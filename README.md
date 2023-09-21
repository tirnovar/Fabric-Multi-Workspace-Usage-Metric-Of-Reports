# Fabric Multi Workspace Usage Metric Of Reports
This notebook works inside Microsoft Fabric with Lakehouse

<img width="1151" alt="Screenshot 2023-09-21 at 16 27 39" src="https://github.com/tirnovar/Fabric-Multi-Workspace-Usage-Metric-Of-Reports/assets/78301524/0d494d28-5fa1-4e1c-a6da-5080bfe55d68">


## Tables created 
Name | Load type | For Report Purposes |
---- | --------- | ------------------- |
ReportLoadTimes | Increment | ✅
ReportPages | Overwrite | ✅
ReportPageViews | Increment | ✅
Reports | Overwrite | ✅
ReportViews | Increment | ✅
Users | Overwrite | ✅
WorkspaceViews | Overwrite | ✅
UsageMetricsDatasets | Overwrite | ❌

## Implemented 
- Generation of Usage Metric datasets
- Time-out handling for workspaces in paused capacities
- Handling for workspaces with VIEW permissions
- Backlog of already existing Usage Metric Datasets in Workspaces
- Handling responses without data
- Incremental DAX query for non-first runs 

## Currently known issues of solution
- Initial load of data from Usage Metric Datasets can contain more than 100k rows or 1M values. (needs to be solved by provided DAX query like in: [Execute Query endpoint - Get your data from datasets](https://datameerkat.com/execute-query-endpoint-get-your-data-from-dataset))
- Initial load to get or generate datasets for Usage Metric can take quite a long time because of the generation process
