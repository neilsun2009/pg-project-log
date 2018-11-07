# Week 10
## 06/11/2018
### Integration of Localization Modules
1. Non-linear LSQ for initialization.
2. Particle Filter for fine adjustment.

### Tracking Worker
1. Get rssi signal measurements from BlockingTrackingBuffer.
2. Check target's latest timestamp to decide whether or not initialize.
3. Get new localization result.
4. Update target's information.
5. The tracking worker should be working in a separate thread.
6. May use while true, as buffer is a blocking list.

## 07/11/2018
### Adding Logs for Tracking Worker
Add useful logs for debug and archive.

### Remaining Problems
1. How to implement the LBS device management. Two maps? List?
2. How to update target information in the LBS device management? Object reference?