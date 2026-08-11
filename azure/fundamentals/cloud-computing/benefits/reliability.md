# Reliability Benefit of Cloud Computing

Reliablity = The ability of a system to recover from failures 

Azure has several built in services that you can use to keep your application running after a failure has occured so your users do not notice or have it quickly fixed if they do notice. 


## Types of failures that can occur: 
- Hardware failure 
- Network interuptions 
- Power failures 
- Large scale regional outage 

## Why is it needed? 
- You have to trust that your cloud provider is doing everything it can to make its platform reliable 
- This includes transparecy 

## How is it achieved? 
- Autoscaling 
- Avoid single points of failure (multiple VMs/instances are better)
- Multi-region deployments (So you can reroute traffic if a region fails)
- Data backup and replication 
- Health probles and self-healing 