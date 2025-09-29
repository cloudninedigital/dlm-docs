---
sidebar_position: 4
---

# Using anomaly detection on even counts (Beta)

Based on daily event counts we run an anomaly detection model, that spots any outliers in the number of events being measured per event. If the number of measured events is higher or lower than the 'upper bound' or 'lower bound' determined from the trained model, an anomaly will be defined and shown in the graph on the UI homepage. 

In the settings tab you can choose whether or not you want to also be notified by flagged anomalies in your main notification channel(s). 

Be aware that the anomaly model does not take into account anything other than the event counts measured. If there's a big sale going on in your company which makes the number of visits on your website increase severely, this will most likely cause an increase in event count and could trigger the flagging of an anomaly. There's always going to be the need for human interpretation in the anomaly model to determine whether or not an actual issue is occuring. 

