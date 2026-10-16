# Kusto Query Language (KQL)
Kusto Query Language (KQL) is the query language used to perform analysis on data to create Analytics, Workbooks, and perform Hunting in Microsoft Sentinel and Microsoft Defender XDR. A KQL query is a read-only request to process data and return results, so when we are on the query console, we can go nuts.

## The anatomy of a KQL query
The query consists of a sequence of query statements. Like this:
```
SecurityEvent
| where EventID == "4626"
| summarize count() by Account
| limit 10
```
At least one statement is a tabular expression statement that produces data arranged in a table-like mesh of columns and rows. Is this example, is the SecurityEvent. The tabular expression statement's syntax has tabular data flow from one tabular query operator to another. Starting with the data source, then flowing through a set of data transformation operators bound together by using the pipe (|) delimiter.
```
Get Data | Filter | Summarize | Sort | Select
```
Here are some of the components of the query:
* Tables: Data source or log type tables (SecurityEvent, SigninLogs, Heartbeat, etc.).
* Operators: (where, summarize, join, etc.).
* Fuctions: (parse\_json(), tostring(), datetime\_diff(), etc.).
* Visualization: (Render)
> [!NOTE] It is good practice to filter your data as early as possible, so you are only passing relevant data down the pipeline.  
