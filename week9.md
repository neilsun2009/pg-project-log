# Week 9
## 30/10/2018
### Integration of MQ Module
1. Class **MQRawSignalDataSource** is responsible for setting up a RabbitMQ consumer instance and return an instance of **RawSignalMeasurement** when asked.
2. Method *init()* will set up a consumer worker. Configurations are listed in class **MQConfig**.
3. Data received will be stored in memory in a queue (LinkedList).
4. Method *get()* will get one measurement from queue and remove it from the queue.
5. *getAll()* will get all the measurements from the queue and clear the queue. This allows the worker to get all the new measurements in the interval between two calculations. 
6. Possible refinement: allow setting up multiple workers, and to achieve that set the queue to be shared among the workers.