Back-of-the-envelope calculations are a crucial part of system design interviews for several reasons:

### 1. **Feasibility and Scalability:**
   - **Estimate Resource Requirements:** These calculations help you quickly estimate the amount of resources (e.g., storage, bandwidth, servers) required for a system. For example, if you're designing a large-scale system, it's important to know whether the proposed architecture can handle millions of users, terabytes of data, or thousands of transactions per second.
   - **Identify Bottlenecks:** By estimating numbers like latency, throughput, and load, you can identify potential bottlenecks in your system before they become real problems.

### 2. **Reasoning and Justification:**
   - **Demonstrate Analytical Thinking:** The interviewer is interested in seeing how you approach complex problems and how you break them down into manageable parts. By performing these calculations, you demonstrate your ability to think critically and make data-driven decisions.
   - **Provide Justifications:** These calculations allow you to justify your design choices. For example, if you choose a specific database technology, you can back up your choice with data on expected read/write rates, query performance, or storage needs.

### 3. **Communication:**
   - **Clarify Assumptions:** Back-of-the-envelope calculations often require you to clarify assumptions (e.g., average request size, number of concurrent users, etc.). This helps both you and the interviewer ensure you're on the same page regarding the scale and scope of the problem.
   - **Engage in Discussion:** These calculations provide a basis for discussion with the interviewer. They allow you to discuss trade-offs, explore alternatives, and refine your design in real-time based on the numbers.

### 4. **Risk Mitigation:**
   - **Spot Potential Issues Early:** By estimating the scale and load of different components, you can anticipate potential issues like database overload, network congestion, or insufficient storage, and adjust your design accordingly.
   - **Plan for Growth:** These calculations help you design systems that are not only viable in the short term but also scalable in the long term, accommodating future growth without major re-architecting.

### 5. **Realism:**
   - **Avoid Over-Engineering or Under-Engineering:** Estimating key metrics ensures that your design is neither over-engineered (wasting resources on unnecessary capabilities) nor under-engineered (failing to meet performance requirements).
   - **Stay Grounded:** In interviews, it’s easy to get carried away with complex ideas. Back-of-the-envelope calculations keep the design grounded in practical reality.

### 6. **Efficiency During Interviews:**
   - **Time Constraints:** Interviews are time-constrained, so you don't have time for detailed calculations or simulations. Back-of-the-envelope estimates provide a quick way to check the viability of your design decisions.
   - **Covering More Ground:** Efficient use of time allows you to cover more aspects of the system, such as data partitioning, consistency models, failover strategies, etc.

### Example of Back-of-the-Envelope Calculation:
If you were asked to design a URL shortening service like Bitly, you might quickly estimate:
- **Storage Requirements:** How many URLs you expect to store, the average length of a URL, and the storage required.
- **Traffic Estimates:** The expected number of requests per second and the required throughput.
- **Database Size:** The total size of your database over time, considering the growth rate of the data.

These quick calculations would help you make informed decisions about the storage systems, caching strategies, and database technologies to use.

### Conclusion:
Back-of-the-envelope calculations are a vital tool in system design interviews because they help you make informed, realistic, and scalable design decisions efficiently. They demonstrate your ability to balance theory with practical considerations, which is a key skill in designing robust systems.