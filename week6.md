# Week 6
## 09/10/2018
### MQ Module
1. As this is a real time application, the need for data durability seems not of great concern, i.e. if the server is down, no calculation is done whatsoever at that time slot, and it's really no use to keep the data. Data acknowledgement, on the other hand, may be remained. If one worker is down, others may assume their work without much time consuming.
2. A more thorough understanding towards this module. The MQ module is more like a middleware and can be deployed on a seperate server. The clients and Java server will use RabbitMQ's communication protocal to connect with the MQ server. The MQ server is afterwards responsible for collecting and distributing message data from producers and to consumers.
3. Add auto reconnection feature on consumer start-up.