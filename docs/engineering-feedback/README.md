# InfoMagnus Engineering Feedback

## When to Submit Engineering Feedback

Capturing and providing high-quality actionable Engineering Feedback is an integral **ongoing** part of all code-with engagements. It is recommended to submit feedback on an ongoing basis instead of batching it up for submission at the end of the engagement.

You should jot down the details of the feedback close to the time when you encounter the specific blockers, challenges, and friction since that is when it is freshest in your mind. The project team can then decide how to prioritize and when to submit the feedback during each sprint.

## What is Good and High-quality Engineering Feedback

Good engineering feedback provides enough information for those who are not part of the code-with engagement to understand the customer pain, the associated product issues, the impact and priority of these issues, and any potential workarounds that exist to minimize that impact.

### High-Quality Engineering Feedback is

* Goal Oriented - states what the customer is trying to accomplish
* Specific - details the scenario, observation, or challenge faced by the customer
* Actionable - includes the necessary clarifying information to enable a decision

### Examples of Good Engineering Feedback

For example, here is an evolution of transforming a fictitious feedback with the above high-quality engineering feedback guidance in mind:

| Stage                       | Feedback Evolution                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Initial feedback            | Azure Functions Service Bus Trigger is slow for in-order scenarios                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Making it **Goal Oriented** | **Customer requests batch receiving for Azure Functions Service Bus trigger with sessions enabled to better support higher throughput messaging. They want to use Azure Functions to process as many messages per second as possible with minimum latency and in a given order.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Adding **Specifics**        | Customer scenario was to receive **a total of 250 messages/second from 50 producers with requirement for ordering per producer & minimum latency, using a Service Bus topic with sessions enabled for ordering. Batch receiving is not supported in Azure Functions Service Bus Trigger.**                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Making it **Actionable**    | Customer scenario was to receive a total of 250 messages/second from 50 producers with requirement for ordering per producer & minimum latency, using a Service Bus topic with sessions enabled for ordering. **According to [Microsoft documentation](https://learn.microsoft.com/azure/service-bus-messaging/service-bus-performance-improvements#prefetching-and-receivebatch), batch receiving is recommended for better performance but this is not currently supported in the Azure Functions Service Bus Trigger. The impact and workaround was choosing containers over Functions. The desired outcome is for Azure Functions to support Service Bus sessions with batch and non-batch processing for all Azure Functions GA languages.** |


