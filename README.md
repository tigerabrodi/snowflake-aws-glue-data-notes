# Data Warehousing

## Facts and Dimensions

A fact table is like a central hub in the database that keeps track of all the important actions and their keys to places containing more information about the specific key.

That place is called a dimension table. A dimension table is a table that contains information about the keys in the fact table.

So a fact table contains both foreign keys and core quantitative data that's commonly desired, also called measures.

## Star Schema

A star schema is a way of organizing the fact and dimension tables in a way that optimizes the data retrieval process. You will have one fact table in the center, and dimension tables surrounding it like a star.

## Snowflake Schema

A snowflake schema is a more complex type of data warehouse schema that is a variation of the star schema. It is called snowflake because its diagram resembles a Snowflake. The fact table is surrounded by dimension tables, which are in turn surrounded by sub-dimension tables.

It is more complex than a star schema and requires more foreign key joins to fetch the data.

# Snowflake

Snowflake is a fully-managed service that provides cloud-based data storage and analytics. It's not just a data warehouse. It's a complete data platform.

## Architecture

Snowflake's architecture is a significant departure from traditional shared-disk or shared-nothing architectures. It's designed as a hybrid of both, optimized for the cloud.

## Three layers

**Database Storage Layer:** This is where all the data is stored. Snowflake manages all aspects of data storage automatically, including organization, file size, structure, compression, and metadata. The storage is highly scalable and can store both structured and semi-structured data.

**Query Processing Layer:** This consists of virtual warehouses (compute clusters) that execute data processing tasks. Each virtual warehouse operates independently, which means that workloads don't compete for compute resources.

**Cloud Services Layer:** This is the brain of the Snowflake environment. It manages tasks like authentication, infrastructure management, metadata management, query compilation and optimization, and access control.

## Virtual warehouses

Think of a virtual warehouse in Snowflake as a powerful computer in the cloud that's dedicated to processing your data. It's not a physical warehouse but a virtual one, where all the heavy lifting of analyzing and querying your data happens.

### Key Concepts

- **Separate From Storage:** In Snowflake, the place where your data is stored (data warehouse) is separate from the place where it's processed (virtual warehouse). This means you can use as much or as little processing power as you need, without affecting your data storage.
- **Scalable:** You can adjust the size of a virtual warehouse to make it more powerful (for faster processing) or less powerful (to save costs) depending on your needs at any given time. It's like having a computer that you can make more powerful or less powerful as needed.
- **Concurrent Usage:** Multiple virtual warehouses can operate at the same time without affecting each other. This is like having several computers, each dedicated to different tasks, so they don't slow each other down.
- **Pay for What You Use:** With virtual warehouses, you only pay for the processing power when you're using it. If the virtual warehouse is turned off, you're not charged for compute resources.
- **Elasticity:** You can turn virtual warehouses on and off as needed. This means you can scale up or down as needed, and you only pay for the processing power when you're using it.

## Data sharing

Snowflake allows for seamless and secure sharing of live data with other Snowflake users. This is done without copying or moving the data, making it a highly efficient process.

## Data cloning and time travel

Snowflake enables creating full copies of databases, schemas, or tables quickly and without additional storage costs. These clones are useful for development, testing, or recovery.

This feature allows users to access historical data (up to 90 days), enabling them to restore data to any point within the specified period or analyze historical data.

## Account Identifiers

The account identifier in Snowflake is a unique identifier that is used to identify a Snowflake account within an organization and throughout the global network of Snowflake-supported cloud services. It includes the name of the account along with its organization and is used in various contexts such as URLs for accessing Snowflake web interfaces, connecting to Snowflake using drivers, connectors, and other clients, and in 3rd-party applications that are part of the Snowflake ecosystem.

## Organizations

An organization in Snowflake is a first-class object that links the accounts owned by a business entity. It simplifies account management, billing, replication, failover/failback, secure data sharing, and other account administration tasks. Organizations allow administrators to view, create, and manage all accounts across different regions and cloud platforms.

# Massive Parallel Processing (MPP)

Massive Parallel Processing (MPP) in data engineering is a way to process huge amounts of data by dividing the work across many different processors (or computers) working at the same time. Think of it like a large team of people working on a big project, with each person handling a small part of the project at the same time.

## How does it work?

**Dividing the Data:** In MPP, the large dataset is divided into smaller chunks. Each chunk is processed by a different processor.

**Processing in Parallel:** Instead of one computer working on the entire dataset (which can be slow), multiple computers (or processors) work on different parts of the data at the same time. This is like having many chefs in a kitchen, each preparing a different dish simultaneously, rather than one chef preparing all dishes one after the other.

**Combining Results:** After each processor completes its task, the results from all processors are combined to form the final output.

## Key Concepts

- It uses a shared-nothing architecture.
- Processors work on separate parts of a task.
- Each processor has its own storage.
- Data and computation are partitioned across multiple nodes (servers), with a leader node coordinating the work.
- It’s scalable by adding more nodes, enhancing performance and handling more users and queries.
- MPP systems typically have high data compression capabilities.
- Processors communicate via a messaging interface.

## Advantages

- Performance improves with more nodes, speeding up computations.
- Scalable to handle larger data volumes by adding nodes.
- Cost-effective as it allows for the use of less expensive hardware.
- No single point of failure; if one node fails, others continue working.
- Easily expandable by adding more nodes

# Batch Processing and Streaming simplified

Batch processing involves analyzing and handling a large volume of data all at once, typically at scheduled intervals.

On the other hand, stream processing involves continuously processing data in real time as it arrives.

The main difference lies in the approach to data processing: batch processing deals with static, finite data, while stream processing handles dynamic, infinite data in real time.

Batch processing is like preparing a week's worth of meals in advance, while stream processing is akin to cooking and serving meals as soon as the ingredients are available.

# Batch Processing

Batch processing is a method of processing large volumes of data or transactions as a single unit, rather than processing them individually in real-time. It is a popular and widely used method for tasks such as payroll processing, billing and invoicing, and data processing for reporting and analysis. Batch processing is often used for tasks that do not require immediate processing and can be scheduled to run at specific times, such as overnight.

- **Data Collection:** In batch processing, data is gathered and stored over a set period. This could be anything from minutes to days, depending on the application and requirements.

**Processing:** Once enough data has been collected, or at a scheduled time, the data is processed as a single batch. This processing can involve computations, data analysis, transformations, or other types of data manipulation.

**Execution Environment:** Batch jobs often run on servers where resources can be dedicated to processing these large volumes of data without user interaction.

**Scheduling:** Batch processes are typically scheduled to run during off-peak hours to minimize the impact on system performance.

**Error Handling:** A key aspect of batch processing is error handling. Since the processing is done on large data sets, identifying and correcting errors can be more challenging.

# Streaming
