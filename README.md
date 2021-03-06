
I just want to build an AKS Cluster to play with the various Data Management capabilities e.g. Backup/Restore, Disaster Recovery and Application Mobility. 

It is challenging to create AKS Cluster from Azure Cloud if you are not familiar to it. After the AKS Cluster is up running, we still need to install Kasten, create a sample database, create location profile, backup policies etc.. The whole process is not that simple.

![image](https://blog.kasten.io/hs-fs/hubfs/Kasten_January2020/Images/microsoft-azure-with-kasten-k10-intro-blog.png?width=1226&name=microsoft-azure-with-kasten-k10-intro-blog.png)


This script based automation allows you to build a ready-to-use Kasten K10 demo environment running on AKS in about 10 minutes. For simplicity and cost optimization, the AKS cluster will have only one worker node in the newly created vnet and subnet. This is bash shell based scripts which has been tested on Cloud Shell. Linux or MacOS terminal has not been tested though it might work as well. 

# Here're the prerequisities. 
1. Go to open Azure Cloud Shell
2. Clone the github repo to your local host, run below command
````
git clone https://github.com/yongkanghe/aks-k10.git
````
3. Create Azure App Registration first
````
cd aks-k10;./createapp.sh
````
4. Optionally, you can customize the clustername, vm size, location, region, containername, etc.
````
vi setenv.sh
````
 
# To build the labs, run 
````
./deploy.sh
````
1. Create an AKS Cluster from CLI
2. Install Kasten K10
3. Deploy a MySQL database
4. Create a location profile
5. Create a backup policy
6. Kick off an on-demand backup job
+ Take a snapshot of Application Components
+ Take a snapshot of Application Configurations
+ Take a snapshot of Workload MySQL
+ Export the snapshot to Azure Blob Storage

# To delete the labs, run 
````
./destroy.sh
````
+ Remove the resource group
+ Remove AKS Kubernetes Cluster
+ Remove all the relevant disks
+ Remove all the relevant snapshots
+ Remove all the storage account

# To kickoff a backup job manually, run 
````
./runonce.sh
````
+ Take a snapshot of Application Components
+ Take a snapshot of Application Configurations
+ Take a snapshot of Workload MySQL
+ Export the snapshot to Azure Blob Storage

# Cick my picture to watch the how-to video.
[![IMAGE ALT TEXT HERE](https://media-exp1.licdn.com/dms/image/C5622AQFZwZJRx80zGw/feedshare-shrink_2048_1536/0/1631701751086?e=1634774400&v=beta&t=sIAsWzAnuGXmbg9QDkPQ_RBYudVvrCipWuMEWfRDO9I)](https://www.youtube.com/watch?v=308ZOMRaRDk)

# AKS Backup and Restore
https://blog.kasten.io/posts/backup-and-recovery-in-microsoft-azure-with-kasten-k10/

# Kasten - No. 1 Kubernetes Backup
https://kasten.io 

# Kasten - DevOps tool of the month July 2021
http://k10.yongkang.cloud

# Contributors

### [Yongkang He](https://github.com/yongkanghe)

