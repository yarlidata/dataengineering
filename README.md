# Slowly Changing Dimensions

## Introduction
Slowly Changing Dimensions (SCD) are a concept used in data warehousing to manage and track changes in dimension data over time. There are several types of SCD, each providing different methods to handle changes in dimension attributes. The primary types are:

## Type 0: Retain Original
Description: No changes are allowed once the data is initially entered. The original data is retained, and no updates are made.
Use Case: Rarely used, applicable where historical accuracy is not crucial.
## Type 1: Overwrite
Description: The existing record is overwritten with the new data. No historical data is preserved.
Use Case: Useful when the history of changes is not important, such as for correcting errors or updating non-critical information.
## Type 2: Add New Row
Description: A new row is added with the updated data. The existing record is preserved, and a new record is created to reflect the change. This often includes a mechanism to identify the current record, such as a start and end date or a current flag.
Use Case: Suitable for tracking historical changes, as it provides a full audit trail of data changes over time.
## Type 3: Add New Attribute
Description: An additional column is added to store the previous value of the attribute. Only limited historical data is stored, typically just the previous value.
Use Case: Effective for scenarios where only the previous value needs to be retained, such as tracking the last job title of an employee.
## Type 4: Add Mini Dimension
Description: A separate dimension table is created to store historical data, while the main dimension table holds the current data. The mini-dimension stores changes separately.
Use Case: Suitable for frequently changing attributes that need to be tracked independently without impacting the main dimension table's size.
## Type 6: Hybrid Approach (Combination of Types 1, 2, and 3)
Description: Combines multiple SCD types to provide a more comprehensive solution. Typically involves overwriting certain attributes (Type 1), adding new rows for historical tracking (Type 2), and adding new attributes for recent changes (Type 3).
## Use Case: 
Utilized when there is a need to retain a combination of current, historical, and prior state data, offering a balance between complexity and data tracking capabilities.
These types offer different strategies for handling changes in dimension data, each with its own advantages and trade-offs. The choice of SCD type depends on the specific requirements of the data warehouse, including the need for historical data retention, query performance, and storage considerations.

Authored by [Yarli Data](https://yarli.com.au) for detailed article at [Blog](https://yarlidata.com/data-warehouse-with-scd-type-2-dimension/)
