## Steps

### run IBMMQ container locally
```
docker run   \
    --env LICENSE=accept   \
    --env MQ_QMGR_NAME=QM1 \
    --env MQ_APP_PASSWORD=passw0rd  \
    --publish 1414:1414   \
    --publish 9443:9443   \
    --detach   \
    ibmcom/mq
    
```

### run test app
```
# compile
javac -cp ./com.ibm.mq.allclient-9.0.4.0.jar:./javax.jms-api-2.0.1.jar com/ibm/mq/samples/jms/JmsPutGet.java

# run
java -cp ./com.ibm.mq.allclient-9.0.4.0.jar:./javax.jms-api-2.0.1.jar:. com.ibm.mq.samples.jms.JmsPutGet
```

```
# Sample output

Sent message:

  JMSMessage class: jms_text
  JMSType:          null
  JMSDeliveryMode:  2
  JMSDeliveryDelay: 0
  JMSDeliveryTime:  1578533549669
  JMSExpiration:    0
  JMSPriority:      4
  JMSMessageID:     ID:414d5120514d312020202020202020209f82165e02f22a21
  JMSTimestamp:     1578533549669
  JMSCorrelationID: null
  JMSDestination:   queue:///DEV.QUEUE.1
  JMSReplyTo:       null
  JMSRedelivered:   false
    JMSXAppID: JmsPutGet (JMS)             
    JMSXDeliveryCount: 0
    JMSXUserID: app         
    JMS_IBM_PutApplType: 28
    JMS_IBM_PutDate: 20200109
    JMS_IBM_PutTime: 01322971
Your lucky number today is 631

```

### 
* https://developer.ibm.com/messaging/learn-mq/mq-tutorials/develop-mq-jms/
* https://github.com/ibm-messaging/mq-container/blob/master/docs/
