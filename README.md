# MessageScheduling
+ This is repository of critical message scheduling for disaster response and recovery phases based on CrisisLexT6 (Crisislex.org) collecting from Server-side proxy application.

+ It contains 6 crisis event below.
  - 2012_Sandy_Hurricane, 
  - 2013_Alberta_Floods, 
  - 2013_Boston_Bombings, 
  - 2013_Oklahoma_Tornado, 
  - 2013_Queensland_Floods, 
  - 2013_West_Texas_Explosion

+ Each event are tested with vary frequency from 100Msg. - 500Msg.

+ Each of testing will be generated the 2 csv. files that will include name
  - ReceiveTweets file {$ServerTime_ReceiveTweets_Msg.Frequency_$SchedulerName{F:R:P}.csv}
    - Ex. 1442069812135_ReceiveTweets_100_P1.csv
  - SnapShot file {$ServerTime_SnapShot.csv}
    - Ex. 1442069812135_SnapShot.csv
  
+ The definition of field in record of ReceiveTweets file is

|Msg.Order|ServerTime|Related{0:1}|Urgent{0:1}|Unique{0:1}|CriticalMsg.{0:1}|RAW_TOPIC|ArrivalTime|Msg.Size(Byte)|RAW_INDEX|RAW_TWEETS|

Ex. 10,1442069813774,0,0,1,0,off-topic,0,73,17,Been jammin to it ever since.
