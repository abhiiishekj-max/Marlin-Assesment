# Part 4: Technical Communication

I selected PR #196 from the aiokafka repository because it was easier for me to understand compared to the other pull requests. It focuses on error handling and retry logic, which are concepts I am already familiar with from my experience in Python.

Many of the other PRs involved deeper Kafka internals, which would have been more difficult to analyze. This PR, however, deals with improving system reliability, which is easier to relate to and understand.

I have some experience working with exception handling and basic backend logic. Because of this, I was able to understand how failures can affect a system and why retry mechanisms are important.

One challenge I expect is correctly identifying which errors should be retried and which should not. If this is not handled properly, it could lead to infinite loops or system crashes. Another challenge is maintaining consistency of internal state after a failure.

To solve these problems, I would focus on proper testing and logging. I would simulate different failure scenarios and observe how the system behaves. I would also follow existing patterns in the repository to maintain consistency.

Overall, I chose this PR because it matches my current knowledge and also helps me improve my understanding of reliable system design.
