## Introduction
![Amazon Data Firehose](amazon-data-firehose.png)

- Use to be called Kinesis Data Firehose
- Fully Managed Service:
	- Amazon Redshift / Amazon S3 / Amazon OpenSearch Service
	- 3rd Party: Splunk / MongoDB / Datadog / New Relic / ..
	- Custom HTTP Endpoint
- Automatic scaling, serverless and pay for what you use
- Near Real-Time with buffering capability based on size/time.
- Supports CSV, JSON, Parquet, Avro, Raw Text, Binary Data
- Conversions to Parquet/ORC, compressions with gzip/snappy.
- Custom data transformations using AWS Lambda (ex, CSV to JSON)