



the workflow listens to event to start the approval and calls jira to create the ticket.
 next we wait for an approved event that the camelK function can implement while listening to the proper webhook. 
 


WEBHOOK-TO-KAFKA

 rest("/jirawebhook")
   .post()
   .consumes("application/json")
   .produces("application/json")
   .to("kafka:{{kafka.topic. incoming jiras}}");




correletion ID - use the jira ID or generate a correlation ID from the calling workflow?

KAFKA-FILTER-APPROVED-TO-SONATA

   
// filter the results and then decide if to send to kafka 
from(uri: "kafaka incoming jiras ")
// filter and send with the jira id
.to("kafka:{{kafka.topic.name of sonata}}");




