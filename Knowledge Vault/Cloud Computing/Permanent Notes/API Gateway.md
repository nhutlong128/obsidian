---
cards-deck: My Deck Name 
tags: dddd, sss
---
### Metadata

-  Type: #permanent #integration 
    Date written: #2021-06-12
    Source:  https://docs.aws.amazon.com/apigateway/latest/
    Status: #wip 
    Keywords:  #cloudcomputing #aws #apigateway
	Related:
	
### Notes
- API Gateway is the API that redirect client request to [[Lambda]], [[HTTP  Endpoint]] or [[AWS Services]]
- API Gateway support 3 API types:
	- Stateless [[API Gateway REST API]] 
	- Stateless [[API Gateway HTTP API]]
	- Stateful [[API Gateway WebSocket API]]
- API Gateway has 3 [[API Gateway Endpoint Type]]
- [[API Gateway Access Control]]
- [[API Gateway Integration Type]]
- [[API Gateway Request Validation]]
- [[API Gateway Template Mapping]]
- [[API Gateway CORS]]
- [[API Gateway Caching]]
- [[API Gateway Usage Plans]]
- [[API Gateway greedy endpoint]]
### Questions

##### You would like to provide a Facebook login before your users call your API hosted by API Gateway. You need seamlessly authentication integration, you will use
- Cognito Sync
- DynamoDB user tables with Lambda Authorizer
- Cognito User Pools
#card 
Cognito User Pools