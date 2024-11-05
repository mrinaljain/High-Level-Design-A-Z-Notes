# Blueprint

## 1. Requirement Gathering for an MVP
Think of all the features required to build a minimum viable product for the users.

### Functional Requirements [3 - 5 Minutes]
Define a list of functional requirements. Functional requirements are the features of the app that the user will be provided with.

- Ask questions / doubts regarding product requirements.
- Features of the platform you are building.
- Functional features contain the features on the user's end.
- Data flow diagram - 0 and DFD - 1 might be helpful initially.

### Non-Functional Requirements
Define a list of non-functional requirements. Non-functional requirements contain backend functionalities related to the product, like consistency, latency, network bandwidth, etc.

Define the following terms for your product:
- **Consistency**: Approach consistency as the main data of your product and think of its consistency.
- **Availability**: The product should be available for use all the time; minor data discrepancies are acceptable.
- **Latency**: Time taken to deliver services to the user after a request.

> **Note**: In case of network failure, decide between consistency and availability based on priority. Also, decide between latency and consistency.

#### Miscellaneous Non-Functional Requirements
Specific requirements related to a particular product. For example: Buffering in OTT.

## 2. Estimation of Scale (Back of the Envelope Calculations)

- **Define the Schema of the Data** to be stored.
- **Requests per second**: Estimate the number of requests your system will receive per second.
- **Storage size of data**: Consider metrics required to measure the platform.
- **Sharding**: Only consider if the feature has database-heavy operations.
- **Read heavy or Write heavy**: Relevant if the user is interacting with the database.
- **Network bandwidth**: Relevant if user interaction is mostly with storage.

### Capacity Estimation (Number of machines?)
Calculate storage size requirements by estimating daily active users and individual data unit size.

1. **Daily Active Users (DAU)**: Estimate DAU for the product.
2. **Percentage of DAU using the specific feature**.
3. **Size of Individual Units**: Calculate daily usage per user.
4. **Data Retention Period**: Set a time frame, such as 5 years, for data storage.

### Network Bandwidth Calculation
1. Estimate daily users.
2. Average time spent per day.
3. Average data usage per user per day.
4. Convert daily data usage to per-second usage.

### Requests per Second Calculation
Estimate total requests per second across all users.

- **Read vs Write Service**: Compare read and write operations to determine if it’s read or write-heavy.
- **Sharding**: Decide based on storage needs and set a sharding key if possible.

### Capacity Estimation Formula
Total Storage = Time * Size of individual unit per user per day * Number of users

## 3. Key Use Cases of System (APIs)
List the APIs required for the feature.

- Determine the necessary APIs for the system to function.
- APIs can support either user or backend functionality.

## 4. Actual High-Level Design (HLD)
Present a flow diagram.

- **Request Flow**: Describe the request journey.
  - Mention major architectural items like App server, Messaging Queue, Database retrieval.
- **Caching**: Outline caching's role in the system.
- **Database**: Specify the database in use.
- **Sharding Process**: Sharding key should minimize cross-shard communications.

## 5. Assumptions
a. 1 Day = 100,000 Seconds  
b. 1 Year = 400 Days  
c. 1 TB = 1 Trillion Bytes  
d. 1 Byte = 8 Bits  
e. 1 KB = 1,000 Bytes (10^3)  
f. 1 MB = 1,000 KB (10^6)  
g. 1 GB = 1,000 MB (10^9)  
h. 1 TB = 1,000 GB (10^12)
