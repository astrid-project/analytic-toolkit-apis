### Node State Diagram
The estimator computes for every **node** and **use-case** a status that can be
one of **"BaU"** (Business as Usual), **"Warning"** or **"Alarm"**.  
If it is not able to compute the status it is in **"Undefined"** status, e.g.
if it has not enough data.  
This diagram shows the transitions between the three states that are governed
by the **use-case** parameters.


```
                    YES                                YES
               +------------------------+        +-------------------------->+
               |                        |        |                           |
               |  error > threshold     |        |  #errors > hysteresis     |
               |                        v        |                           v
+--------------+--+  NO         +-------+--------+--+  NO           +--------+-----+
|                 +-----+       |                   +-----+         |              |
|   Business      |     |       |     Warning       |     |         |    Alarm     +<---+
|   as Usual      |     |       |                   |     |         |              |    |
|                 +<----+       |                   +<----+         |              |    |
+------+----------+             +-------------------+ #errors+=1    +------+-+-----+    |
       ^                                                               NO  | | YES      |
       +-------------------------------------------------------------------+ +----------+

                                                                     error > threshold
```
