# Week 9
## 30/10/2018
### Integration of MQ Module
1. Class **MQRawSignalDataSource** is responsible for setting up a RabbitMQ consumer instance and return an instance of **RawSignalMeasurement** when asked.
2. Method *init()* will set up a consumer worker. Configurations are listed in class **MQConfig**.
3. Data received will be stored in memory in a queue (LinkedList).
4. Method *get()* will get one measurement from queue and remove it from the queue.
5. *getAll()* will get all the measurements from the queue and clear the queue. This allows the worker to get all the new measurements in the interval between two calculations. 

## 31/10/2018
### More on MQ Module
1. Possible refinement: change the structure to allow setting up multiple workers: set the queue to be shared among the workers. This will be useful if dealing with high throughout.
2. For the time being, there is only one direct exchange with one routing name, this could be augmented in the future if necessary.

## 01/11/2018
### Message Standard for MQ
1. JSON format.
2. 
``` JSON
{
  "sensorId": 123456, // number
  "sensorType": 1, // number, wifi or bluetooth
  "time": 1541057709, // number, UNIX timestamp, to second
  "measure": [
    {
      "tagId": 654321, // number
      "tagType": 2, // number, wifi or bluetooth
      "rssi": -60, // number
      "time": 1541057708 // number, timestamp
    }
  ]
}
```
### Add JSON Processing
Use org.json package. See more in [1].

### Reference
1. JSON in Java https://blog.csdn.net/flyliuweisky547/article/details/19172133
