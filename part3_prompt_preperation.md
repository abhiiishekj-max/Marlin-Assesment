# Part 3: Prompt Preparation

## Selected PR: aiokafka #196

---

## 3.1.1 Repository Context

The aiokafka repository provides an asynchronous Kafka client for Python. It is designed to allow developers to build scalable and efficient systems that handle large volumes of data in real time.

The repository is mainly used by backend developers and data engineers. It is especially useful in systems where multiple services communicate using Kafka, such as microservices architectures.

The main problem it solves is enabling non-blocking communication with Kafka. Traditional clients may block execution, but aiokafka uses asynchronous programming to improve performance and scalability.

---

## 3.1.2 Pull Request Description

This pull request improves how the Kafka consumer handles errors. Previously, when failures occurred, the system could stop or behave incorrectly. This was mainly due to poor handling of network issues and broker failures.

The PR introduces retry logic for temporary failures and ensures that internal state is reset correctly. It also separates recoverable errors from fatal ones.

With these changes, the consumer becomes more reliable and can continue working even when temporary issues occur. This improves overall system stability.

---

## 3.1.3 Acceptance Criteria

✓ The system should retry message fetching after a network failure  
✓ Internal state should be reset correctly after errors  
✓ The consumer should not run with invalid state  
✓ Logs should show retry attempts clearly  
✓ Fatal errors should stop execution properly  

---

## 3.1.4 Edge Cases

- Broker disconnect during message fetch  
- Invalid or corrupted offsets  
- Continuous failures causing retry loops  

---

## 3.1.5 Initial Prompt

You are working on the aiokafka repository, which is an asynchronous Kafka client written in Python. Your task is to improve the reliability of the Kafka consumer by implementing better error handling and retry logic.

Currently, the consumer does not handle failures properly. When network issues or broker failures occur, it may stop working or continue with an inconsistent internal state.

You need to implement the following:

- Add retry logic for temporary failures  
- Reset internal state such as offsets and partitions after errors  
- Differentiate between recoverable and fatal errors  
- Improve logging for debugging  

Acceptance Criteria:

- The consumer retries operations after temporary failures  
- Internal state is validated before continuing  
- The system does not continue in an invalid state  
- Logs clearly show retries and failures  
- Fatal errors stop execution safely  

Edge Cases:

- Network failure during message fetch  
- Corrupted offsets  
- Repeated failures  

Testing Requirements:

- Simulate failure scenarios  
- Verify retry behavior  
- Ensure no data duplication or loss  

Ensure that the solution follows asynchronous programming principles.
