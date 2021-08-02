### Metadata

-  Type: #permanent #networking
    Date written: #2021-06-27
    Source:  https://docs.aws.amazon.com/route53
    Status: #wip 
    Keywords:  #cloudcomputing #aws #route53
	Related:
	
### Notes
- [[Route 53]] is [[Managed DNS]]
![[Pasted image 20210627213917.png]]

- [[Route 53 Record Types]]

- [[Route 53 Record TTL]]: browser caching only the period of TTL seconds and then will send request to [[Route 53]] again
![[Pasted image 20210627220023.png]]

- [[Route 53 Routing Policy]]

- [[Route 53 Health Checks]]
![[Pasted image 20210627223628.png]]

### Questions

##### You have purchased "mycoolcompany.com" on the AWS registrar and would like for it to point to `lb1-1234.us-east-2.elb.amazonaws.com` . What sort of Route 53 record is **NOT POSSIBLE** to set up for this?
- CNAME
- Alias
#card 
CNAME. The DNS protocol does not allow you to create a CNAME record for the top node of a DNS namespace (mycoolcompany.com), also known as the zone apex.

##### You have deployed a new Elastic Beanstalk environment and would like to direct 5% of your production traffic to this new environment, in order to monitor for CloudWatch metrics and ensuring no bugs exist. What type of Route 53 records allows you to do so?
- Simple
- Weighted
- Latency
- Failover
#card 
Weighted

##### After updating a Route 53 record to point "myapp.mydomain.com" from an old Load Balancer to a new load balancer, it looks like the users are still not redirected to your new load balancer. You are wondering why...
- it's because of the alias record!
- it's because of the CNAME record!
- it's because of the TTL
- it's because of the health checks
#card 
it's because of the TTL. DNS records have a TTL (Time to Live) in order for clients to know for how long to caches these values and not overload the DNS with DNS requests. TTL should be set to strike a balance between how long the value should be cached vs how much pressure should go on the DNS.

##### You want your users to get the best possible user experience and that means minimizing the response time from your servers to your users. Which routing policy will help?
- Multi Value
- Weighted
- Latency
- Geo Location
#card 
Latency

##### You have a legal requirement that people in any country but France should not be able to access your website. Which Route 53 record helps you in achieving this?
- Latency
- Simple
- Geo Location
- Multi Value
#card 
Geo Location

##### You have purchased a domain on Godaddy and would like to use it with Route 53. What do you need to change to make this work?
- Request for a domain transfer
- Create a private hosted zone and update the 3rd party registrar NS records
- Create a public hosted zone and update the Route 53 NS records
- Create a public hosted zone and update the 3rd party registrar NS records
#card 
Create a public hosted zone and update the 3rd party registrar NS records. Private hosted zones are meant to be used for internal network queries and are not publicly accessible. Public Hosted Zones are meant to be used for people requesting your website through the public internet. Finally, NS records must be updated on the 3rd party registrar.
