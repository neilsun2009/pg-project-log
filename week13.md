# Week 13
## Program Entrance of Server
1. Set new threads for workers to enable the full process of retrieving data, buffering and tracking.
2. Procedure:
+ Initialize RabbitMQ consumer
+ Use MQ data source and data buffer to initialize data preprocess worker, and run it in a seperate thread
+ Run tracking worker in another thread

## Remaining Work
1. Conversion from RSSI to distance in tracking worker. A skeleton of the signal propagation model is listed, with parameters to be set. (TrackingWorker.java)
2. Saving of tracked data. May update data in hibernate. (TrackingWorker.java)
3. Details in Hibernate & Dao. May add other members other than ID for sensor and target.(mosent.dev)
4. Parameters for worker interval. May change the interval for DataPreprocessWorker to be more reasonable, and may add an interval for TrackingWorker (it runs currently using while true + blocking queue). (Mosent.java)
5. Sensor location data source. May use RabbitMQ to convey data (routing name defined in datasrc/signal/mq/MQConfig.java).
6. Possible RabbitMQ configs update. (datasrc/signal/mq/MQConfig.java)
7. Overall test. Individual modules have been tested, an overall test is to be conducted.
