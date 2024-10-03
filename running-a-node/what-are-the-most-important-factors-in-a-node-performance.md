# What are the most important factors in a node performance?

_By:_ [_Cassandra Heart_](https://warpcast.com/cassie) _- Source:_ [_Q Forum_](https://quilibrium.discourse.group/t/what-are-the-most-important-factors-in-performance/311/1)

***

One of the things that has come up is the topic of which kinds of machines work better for Q. I’ve tried to stress repeatedly that machine differences can sometimes cause almost paradoxical outcomes when operating on simple guidance. This post will hopefully exhaustively outline all the scenarios which come into play in choosing hardware with the most ideal configuration.

#### **What is the general guidance?**

Previously, I have quipped a few simple tips, but unfortunately this has been a poor answer, because there are too many factors that aren’t being taken into consideration if simply choosing one particular piece of advice – all must be considered. Here are the list of tips and expectations that I’ve previously given, but with proper context:

* More cores, more rewards: Comparing two identical processor architectures (i.e. not across x64, but literally Zen 3 to Zen 3), with identical clock speeds, L1/L2/L3 cache sizes, core allocations thereof, RAM speed, CAS latency, more cores will yield more rewards.
* Clock speed matters: Comparing two identical processor architectures, a higher clock speed will naturally compute _faster_, meaning the faster processor will accumulate more rewards in the same time.
* 10-15 second proof times should near 3-4 second proof times by 2.0: for machines taking 10-15 second proof times, they should see approximately a 3-5x speedup over time, because they will accelerate through iterations fast enough to reduce the difficulty to a value that will be approximately 3-4 seconds by the time of 2.0.

This last one is by far is the most contentious one, because there are many assumptions that can be made out of that statement. This one in particular I want to unpack deeper in the context of the priors because it will help explain how this can be the case while some systems have seen minimal increase.

#### **What’s in the VDF?**

The Wesolowski VDF is performing a variation of the repeated squaring arithmetic originally defined in the paper [“Time-lock Puzzles and Timed-release Crypto”, by Rivest, Shamir and Wagner](https://people.csail.mit.edu/rivest/pubs/RSW96.pdf). Unlike the classical timelock paper, where the order of the group is known to one party, meaning it is ill fitted for a VDF, Wesolowski uses IQC, where the order is not known to any party, and finding it is NP hard. The implementation of Wesolowski has two particular aspects which can cause vast behavioral outcomes on hardware that at first glance appears to be roughly approximate: branch prediction, cache size and degree of which the caches are shared.

#### **Branch Prediction**

The arithmetic required to perform repeated squaring under IQC requires frequent iteration over a number of branching conditions, which will result in a processor making branch predictions in order to be efficient. Architectures vary in their complexity of branch predictors, and some have proven to have serious problems in terms of side channels for leaking information.

The issue with branch prediction implementations, regardless of side channels, is when they miss – this can be especially frequent in arithmetic whose outcomes are intended to be random in nature. Mispredictions cost extra time, and it can be especially worse on some architectures.

#### **Caches**

Loading data from memory is not free – to alleviate this, processors will employ layers of caches which vary somewhat across even the same architecture, in size, and degree of sharing involved between cores. A larger L1, L2, and L3 cache generally\* (this is a load bearing word) results in faster applications as they have to make fewer fetches from memory. That being said, even the cache can produce interesting consequences for timings, as a cache miss can be more expensive on certain architectures.

One of the easiest demonstrations of this is how certain very high end Zen architectures running at high clock speeds (4GHz) may perform _worse_ than an M1 Max (3.2GHz) core-for-core – the M1 has better branch prediction and cache performance for the VDF, and likely is seeing some advantages in the RAM.

#### **Time is relative**

The last piece to contextualise the proof speedup is also a matter of time – the linear relation of proof iterations to difficulty: `difficulty = 200000 - (iterations/4)`. The time from 1.4.19’s release to 2.0 is a specific window of real world time: four to six weeks. VDF calculations of difficulty have a range of real world times they may take. So let’s revisit the 10-15s example: Assuming a true interval time of 10s, taking a sum of `10*((200000-(n/4)))/200000), n=0 to 100000` (e.g. the total time taken to reach 100000 iterations, assuming a truly linear scale of iterations to time) yields 937,509 seconds, or approximately 11 days. At about 300,000 iterations, following this linear scale, 28 days would have passed, and the 10s would be down to \~6s for a single iteration.

There’s a catch here, because that’s not 3-4s, and I _did_ say 3-4 seconds, right? Sure, one could argue the linear relation does reach that point assuming a 1.4.21, but the 15s case _doesn’t_. So where’d that number come from?

The problem with the above formula is the relationship isn’t actually linear – Wesolowski requires more memory for greater difficulty, which results in more cases for branch and cache mispredictions, more times the memory bandwidth will be a factor. So the reduction in time is actually _greater_ over time, the only thing is, where that reduction starts kicking in doesn’t only depend on the number of iterations, it depends on the earlier described factors.

To find the ideal hardware, it’s ultimately going to take a lot of data – collectively, we’ll need to pool information on what has produced the greatest performance. While the decreasing difficulty is only a consideration of the 1.4.x series, it will still be extremely helpful in 2.0.
