# Implementing the Blue/Green deployment for RDS Aurora

- What problem we are solving here
- Overview
- How to implement
- Benefits  
## Problem statement(s)
- When you have to upgrade the major or minor DB engine version or
- When we have to change database parameters or 
- When we have to make schema changes in the staging environment
- Will my production workloads be impacted?
  - Will I have down time? how much?
  - Will I loose my production data?
  - Will I have to do application changes?
  
## Overview
A blue/green deployment copies a production database environment to a separate, synchronized staging environment. By using Amazon RDS Blue/Green Deployments, you can make changes to the database in the staging environment without affecting the production environment.

By using Amazon RDS Blue/Green Deployments, you can make and test database changes before implementing them in a production environment. A blue/green deployment creates a staging environment that copies the production environment. In a blue/green deployment, the blue environment is the current production environment. The green environment is the staging environment. The staging environment stays in sync with the current production environment using logical replication.

You can make changes to the Aurora DB cluster in the green environment without affecting production workloads. For example, you can upgrade the major or minor DB engine version or change database parameters in the staging environment. You can thoroughly test changes in the green environment. When ready, you can switch over the environments to promote the green environment to be the new production environment. The switchover typically takes under a minute with no data loss and no need for application changes.

