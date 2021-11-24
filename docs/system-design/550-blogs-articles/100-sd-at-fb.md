---
sidebar_position : 100
tags:
  - facebook
---

# System Design Interview at FB

I have done a lot of interviews at FB and have seen several patterns that can help people be more successful. Note: this is my personal observations.

I think my observations might help people interviewing for E5 the most, and hopefully not just at FB but other tech companies as well.

1. You don't lead the conversation. At FB, E5 is senior SWE, you are expected to lead. During system design interview, we expect you to lead the conversation. If you cannot do that effectively, very likely I will down level you to E4.

2. You don't pay enough attention to Problem Exploration. Very often, candidates ask a couple simple questions to verify the problem and move on, jump right into the solution/design. It's not a good practice. I recommend structure it better, at least break down the problem clearly to 2 parts: Functional requirements, and Non-function requirements. Describe your assumptions and ask for clarification.

3. You don't do quantitative analysis or you do it incorrectly. Some people ignore that part. If you don't understand the scale of the system, QPS, database size, database growth, how would you design a scalable system. Now, it's even more interesting. Many people did quantitative analysis as recommended in many interview guideline. But it's fking useless if you don't use the information there to justify your design decisions/tradeoffs. In short, many people only do some quantitative analysis to complete an item in the checklist.

4. You don't actively discuss your design decisions and tradeoffs. Sometimes you think it's obvious, but as an interviewer, I don't know if you have consider other options. You'd better discuss some alternatives and why you decide to go with your choice. For example why you use MySQL vs K/V store.

It sounds very basic, but from my own experience, 90% of candidates make at least 1 or more of these mistakes.

How would you approach it? This is what I would do, and what I have seen successful candidates do.

1. Clarify functional and non-functional requirements.
2. The non-functional requirements should include the capacity or scalability requirement. Go from there to do some quantitative analysis.
3. Start with a basic design (similar to the brute-force solution in coding). Express clearly that this is the basic design and you will evolve it from there. Note: even for the basic design, you should start talking about tradeoffs of your design decisions.
4. Now, use the analysis in 2. to evolve your design. Do you need to add LB, caching, sharding, pre-computing etc? Why?

This is quite enough for a senior SWE in 40'. For higher levels, you should be able to go deeper and broader for 4 and I will not go into the detail here. Also, go broader might help as well. For example, if the question as you to design something for photos, think about how you would extend it to videos and other content types as well.
