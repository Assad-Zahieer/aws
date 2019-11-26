# AWS Batch
## Overview
* manage batch computing workloads
* Batch processing - series of processes
* Batch computing - Lots of power across cluster of compute resources to complete batch process
## 1. Components
**Jobs** - Unit of work run by aws batch as containerised app
**Job definitions** - dictate how job will run and infrastructure configuration
**Job queues** - Move jobs into job queue
    * Multiple queues based on priority
**Job scheduling** - when and where job runs
**Compute environment** - contain compute resources required for jobs
## 2. Use Case
* Run mulitple jobs in parallel
    * e.g. analyse financial risk models
