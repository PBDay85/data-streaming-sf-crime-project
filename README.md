# data-streaming-sf-crime-project
Project files for the san francisco crime project for data streaming nano degree

Two questions requiring answering within the readme:

1. How did changing values on the SparkSession property parameters affect the throughput and latency of the data?

Increasing the trigger process time increases latency but can increase throughput. This works in tandem with the max offsets per trigger to ensure that not too many offsets are processed in a batch (which means the processing time may be longer than the trigger time) or two small to reduce the processed rows per second.


2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?

Testing the most optimal is possible by looking at the processed rows per second and the input rows per second on the progress report. 1000 offsets per second, with max rate of 100 and trigger time of 10 seconds worked well relative to those values around it, processing 135 rows per second.
