Goals
============

A simple,extensible tool for  performance benchmark testing of common storage service.

Core Framework
============
Input: Abstraction for query set input, can be customized
Query: Abstraction for single query, intermidate stable representation for various query formats.
QueryReader: Will be called by framework for reading single query from input and parse it to Query object, can be customized.
QueryWriter: Will be called by framework for translating Query object to target request string,can be customized.
Response: Abstraction for single query response, intermidate stable representation for various response formats.
ResponseReader:Will be called by framework for reading single response and parse it to Response object,can be customized
Output: Statistics information for testing, will called by framework to collect responses and generate testing result.
        Can be customized.
Channel: Framework will create some channels to send query, channel can be binded with customized protocol handler.
Protocol Handler:Can be customized, will be called by Channel for talking to backend storage service.HTTP,KFC will be supported
                 ,and it also can be customized.


Use Cases
============
./simple_bench --parellel=10 --input=hdfs://...  --query_reader=default --query_writer=default --response_reader=default --output=default --protocol=HTTP 