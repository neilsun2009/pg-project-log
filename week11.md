# Week 11
## Project Report
+ Structurize the contents of project report.
+ Finish chapter 1.

## Test on JSON Retrieval in MQ
+ Generate test JSON string to be used in Android simulator.
+ Test data: 
```json
{"sensorId":123456,"sensorType":1,"time":1541057709,"measure":[{"tagId":654321,"tagType":2,"rssi":-60,"time":1541057708},{"tagId":654322,"tagType":2,"rssi":-40,"time":1541057707}]}
```
+ Test the functionality of JSON retrieval, raw mq data get one and get all.
+ Disable data aknowledgement for MQ, as when message of wrong format comes it, the system will crack even after restart (data not yet acknowledged will keep on waiting to be examined).
+ Add try/catch around JSON handler, the MQ consumer will not be interrupted when encounter bad inputs.
## Data Preprocess Worker
+ Implement data preprocess worker.
+ Similar to track worker, require main function's unique thread to set an interval of running the worker.
+ Use HibernateDAO to get sensors and targets.
