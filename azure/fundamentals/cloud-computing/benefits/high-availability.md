# High Availability Benefit of Cloud Computing

 HA = The ability for a system to remain operational to users during planned or unplanned outages 

## Planned Outages: 
 - OS sec patches
 - App updates
 - Hardware replacements
 - Migrating to a new host provider

## Unplanned Outages: 
 - Hardware failure
 - Network distruptions 
 - Power outages
 - Natural disasters 
 - Cyber attacks 
 - Software bugs 
 - Poor scaling / architecture design 


## Methods to Mitigate Planned Outages: 
- Gradual deployment strategy
- - 1 (server) - 10 (servers) - 100 (servers)-etc
- Testing and monitoring deployment 
- Easy rollback plan 
- Small deployments
- Frequent deployments (lower chances of things going wrong)
- Automation 

## Methods to Mitigate Unplanned Outages: 
- Every core component has redundancy 
- Use AZURE's built in features for availability 
- - Availability Sets
- - Availability Zones
- - Cross-region load balancing / Front Door
- Constant health monitoring / probes
- Automation  
- Strong security practices 
- Geographically distrubting servers 
- Have disaster recovery plan 
- Test that disaster recovery plan / fire drills
- Load testing




