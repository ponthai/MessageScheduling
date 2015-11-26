# MessageScheduling
+ This is repository for research purpose
+ Research Topic on "Critical Message Scheduling for disaster scenario"

+ Based on CrisisLexT6 (Crisislex.org) collecting from Server-side proxy application.

+ It contains 6 crisis event below.
  - 2012_Sandy_Hurricane, 
  - 2013_Alberta_Floods, 
  - 2013_Boston_Bombings, 
  - 2013_Oklahoma_Tornado, 
  - 2013_Queensland_Floods, 
  - 2013_West_Texas_Explosion

+ Each event are tested by varying frequency from 100Msg. - 500Msg.

+ Each testing will be generated the 2 files (.csv)
  (1) ReceiveTweets file "[$ServerTime]_ReceiveTweets_[$Msg.Frequency]_[$SchedulerName{F:R:P}].csv"
  - This file contains every received messages at Server-side proxy (message by message) 
    - Ex. 1442069812135_ReceiveTweets_100_P1.csv

  - The definition of fields in the record of ReceiveTweets file (1) is
    >Msg.Order,ServerTime,Related{0:1},Urgent{0:1},Unique{0:1},CriticalMsg{0:1},
    TOPIC,ArrivalTime,MsgSize(Byte),INDEXOriginal,TWEETS
    >Ex. 10,1442069813774,0,0,1,0,off-topic,0,73,17,Been jammin to it ever since.
  
  (2) SnapShot file "[$ServerTime]_SnapShot.csv"
  - This file contains only critical message at Server-side proxy (SUM Critical message/10second)
    - Ex. 1442069812135_SnapShot.csv
    
  - The definition of fields in the record of SnapShot file (2) is
    >AtSecond,SUM(CriticalMsg),SUM(ALLMsg),SUM(MsgSize(Byte))
    >Ex. 10,18,520,56536

