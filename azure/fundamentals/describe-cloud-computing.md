# Cloud Computing

### What is cloud computing? 
- Cloud computing basically means renting computing resources over the internet instead of owning and running all the hardware yourself.

## Shared Responsiblity Model
### On Premise
### Cloud Virtual Machine Responsibility
### Cloud App Service Responsiblity 
### Cloud SaaS Responsibility (mixed/shared)
- Shared responsbility of Authentication platform 

## Azure Shared Responsibility Model

| Responsibility | SaaS | PaaS | IaaS | On-Premises |
|---|:---:|:---:|:---:|:---:|
| **Information and data** | 🟦 Customer | 🟦 Customer | 🟦 Customer | 🟦 Customer |
| **Devices (Mobile and PCs)** | 🟦 Customer | 🟦 Customer | 🟦 Customer | 🟦 Customer |
| **Accounts and identities** | 🟦 Customer | 🟦 Customer | 🟦 Customer | 🟦 Customer |
| **Identity and directory infrastructure** | 🔀 Shared | 🔀 Shared | 🟦 Customer | 🟦 Customer |
| **Applications** | ⬜ Microsoft | 🔀 Shared | 🟦 Customer | 🟦 Customer |
| **Network controls** | ⬜ Microsoft | 🔀 Shared | 🟦 Customer | 🟦 Customer |
| **Operating system** | ⬜ Microsoft | ⬜ Microsoft | 🟦 Customer | 🟦 Customer |
| **Physical hosts** | ⬜ Microsoft | ⬜ Microsoft | ⬜ Microsoft | 🟦 Customer |
| **Physical network** | ⬜ Microsoft | ⬜ Microsoft | ⬜ Microsoft | 🟦 Customer |
| **Physical datacenter** | ⬜ Microsoft | ⬜ Microsoft | ⬜ Microsoft | 🟦 Customer |

**Legend**
- 🟦 **Customer** — Your responsibility
- ⬜ **Microsoft** — Cloud provider's responsibility
- 🔀 **Shared** — Responsibility is shared/varies


### What is Public Cloud? 
- The public cloud is defined as computing services offered by third-party providers over the public internet, making them available to anyone who wants purchase them. 
- In this case Azure owns the hardware, on their network and infrastructure.

### What is the Private Cloud? 
- The private cloud is defined as computer services offered either over the Internet or a private internal network and only to select users instead of the general public. 
- So it's the same as a public cloud but the customer owns or leases or has exclusive access to the hardware. 

### What is hybrid cloud? 
- The combination of a public and private clouds; scale private infrastructure to the cloud. 

--------------------

### Consumption Based Model 
- You only pay for what you use. 
---------------------------------------



### Cloud Pricing
- Difficulty to predict monthly bill 
- Difficult to understand in advance what a service will really cost
- Possiblity for big savings but you lose predictability 

#### Factors affecting VM pricing 
- Geo region 
- OS SKU/License
- Instance Size
- Disk type/size
- Bandwith
- Backup Storage
- Reservation/Savings plan
- Support agreement 

#### Factors affecting cosmos DB pricing
- API choice
- Region/Regions (number of regions you replicate your data to)
- Standard Model/ Serverless Model 
- Number of operations per second
- Consumed storage
- Optional dedicated gateway
- Backup storage

To help manage this... 

#### Free Services 
- 55+ free services that can be used as part of your solution 
- Some paid services have free tiers 
- Some have limits 

#### Pay for time 
- Some services charge for time used 
- Stop using the service, stop the charges 
- VM instances

#### Pay for GB
- Usually pay for any data storage used 
- Fairly cheap  - 2 pence or less per GB per month
- Also pay for network traffic to/from other regions or to the internet

### Pay for operations 
- You can also be charged per operation 
- Operations are read, write, list, delete
- Pay per message, per query to a database, etc 
- Usually very cheap per operation 