# Protocol Definition

## Structure
We pad every message with 8 bytes containing the length of the message as a
unsigned integer. The following message is a GZIP compressed wire formatted
protocol buffer message <RequestContainer> or <ResponseContainer>.
```
+-------------------------+-----------------+
|   Message Length (n)    |     Message     |
|-------------------------+-----------------+
|       8 bytes           |     n bytes     |
+-------------------------+-----------------+
```

## Build:
To generate the C++ representation of the messages:
```
$ mkdir build
$ protoc --proto_path=./protos/ --cpp_out=./build/ container.proto graph.proto shortest_path.proto <other_response_request_message>.proto
```

To generate the Python representation of the messages:
```
$ mkdir build
$ protoc --proto_path=./protos/ --python_out=./build/ container.proto graph.proto shortest_path.proto <other_response_request_message>.proto
```

