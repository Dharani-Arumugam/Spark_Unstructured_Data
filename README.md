## Spark Unstructured Data Processing
This project process stuructured and Unstructured data using Apache Spark and store into Amazon S3 as parquet files.
Using Amazon Glue Crawler, data from S3 is being read and schema is created. Then used Amazon Athena to run the query to fetch the results.
#### Docker Start
~~~
docker compose up -d
~~~


#### Spark Process using Docker
~~~

docker exec -it spark-master /opt/spark/bin/spark-submit \
--master spark://spark-master:7077 \
--conf spark.jars.ivy=/tmp/.ivy2 \
--packages org.apache.hadoop:hadoop-aws:3.3.1,com.amazonaws:aws-java-sdk:1.11.469 \
--py-files /opt/spark/jobs/udf_job_bulletins.py \
/opt/spark/jobs/main.py

~~~
