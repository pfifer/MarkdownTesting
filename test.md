## Release Test
* Added support for something
  * Nice API
  * Added configuration stuff usage  
  
     | Name | Default | Description |
     | ---- | ------- | ----------- |
     | Latency Mode | 1500 ms | What is latency? |
     | Failure Mode  | 50 | How do we fail |
   
  * [PR#]()
* Updated the version of something
   * Version is cool new version
* Deprecated the stuff
  * Deprecated Thing 1
  * Deprecated Thing 2
  * Deprecated Thing 3


### Release 1.8.8
* Fixed issues with leases losses due to `ExpiredIteratorException` in `PrefetchGetRecordsCache` and `AsynchronousFetchingStrategy`.  
  PrefetchGetRecordsCache will request for a new iterator and start fetching data again.  
  * [PR#263](https://github.com/awslabs/amazon-kinesis-client/pull/263)
* Added warning message for long running tasks.  
  Logging long running tasks can be enabled by setting the following configuration property:
  
  | Name | Default | Description |
  | ---- | ------- | ----------- |
  | [`logWarningForTaskAfterMillis`](https://github.com/awslabs/amazon-kinesis-client/blob/3de901ea9327370ed732af86c4d4999c8d99541c/src/main/java/com/amazonaws/services/kinesis/clientlibrary/lib/worker/KinesisClientLibConfiguration.java#L1367) | Not set | Milliseconds after which the logger will log a warning message for the long running task |
  
  * [PR#259](https://github.com/awslabs/amazon-kinesis-client/pull/259)
* Handling spurious lease renewal failures gracefully.  
  Added better handling of DynamoDB failures when updating leases.  These failures would occur when a request to DynamoDB appeared to fail, but was actually successful.  
  * [PR#247](https://github.com/awslabs/amazon-kinesis-client/pull/247)
* ShutdownTask gets retried if the previous attempt on the ShutdownTask fails.
  * [PR#267](https://github.com/awslabs/amazon-kinesis-client/pull/267)
* Fix for using maxRecords from `KinesisClientLibConfiguration` in `GetRecordsCache` for fetching records.
  * [PR#264](https://github.com/awslabs/amazon-kinesis-client/pull/264)
