# CERN School of Computing on IT Services 2025

## MON, AM. Sebastien Ponce – A bit of physics in a week of computing

- 4 missions of CERN: Research, Technology, Collaborating, Education
- Accelerators:
	- Generator sinusoidal for a linear accelerator: Radio freq cavity (e.g., LINAC 4)
	- Circular accelerator: in LHC 1232 bending magnets, 8 sectors/octants
	- Magnets for squeezing the beams, beta functions
- Detectors:
	- We want to find the particules that lived for a short period of time
	- Calorimeter to stop light densed particules: electron, proton (ECAL), second and stronger to stop, kaon, pion, ... (HCAL) but let pass muons
- Triggers:
	- Reconstruction of data (we want to know what particule, what ...)
	- Keep 0.1% of data (from 5TB/s to 10GB/s)
- Storage: 1ExaByte

## MON, AM. Andrzej Nowicki – DB Services (1/4), Intro to DB

- `create table customers (CustomerId number, Name varchar2(20));`
- `insert into customers values (123, 'Alice');`
- CAP theorem (Brewer's theorem):
	- In db you can only have 2 out of 3: Consistency, Partition Tolerance (to network), Availability
	- Ideally we want consistency: Atomicity, consistency, isolation, durability: ACID
	- BASE eventual consistency
- How to make your db resilient? Storage > Datafiles > Server > Application
- Highly available database system: Storage (with copies), multiple servers, a load balancer
- Disaster Recovery (DR): replicated in Prevessin
- Backups
- Test the recovery
- Why backups < DB? 1. replication, 2. compression, 3. dev and test we don't back it up

## MON, PM. Abhishek Lekshamanan, Gianmaria Del Monte – Storage (part 1 of 2) and re-requisites

- 300PB of raw data on tape every year
- Heterogeneous H/W support
- Basic Storage Terminology:
	- Block size = unit of an IO operation (4kiB in HDD, 64kiB in SSD)
	- Latency = duration of IO request to completion
	- IOPS = measure of I/O operation per second for a given blocksize
	- Throughput/Bandwidth = Rate of data transfer
	- Higher IO size = more throughput, lesser IOPs
	- Throughput = IOPS x Block_size
- Tapes:
	- 50TB max, 40MB/s, 1km long, 34h to fill
	- Lowest price per TB and good for cyber-security
- RAID - Redundant Array of Independent Disks: multiple drives combined into one logical unit
	- RAID 0, you write files in multiple disks
	- RAID 1, write 2 times, data mirroired across n disks
	- RAID 5, striping with distributed parity
	- RAID 6, striping with dual distributed parity
	- RAID 10, combined mirroiring and striping RAID 1 + 0
- EOS Open Storage
	- To solve analysis use case for LHC
	- MGM (access mode, acl) is stateless
- EOS uses Xrootd
- For personal data, all CERN accounts have a RB of personal space
- Best practices:
	- If analysis large files, prefer remote access protocols, accessing files in ROOT/pyroot with urls
	- For batch jobsm do not use EOS as a working dir to synch:
		- Use local dir & HTCCondor Xroot pluggins
- If sharing of data is not necessary e.g., in your VM, container, avoir using filesystems
- CERN Box:
	- Powered by Reva https://github.com/cs3org/reva
	- There is a recycle bin that can be accessed through the CLI
	- It is mounted on lxplus, /eos/user/g/...
- Ceph:
	- CRUSH - Controlled Replication Under Scalable Hashing
	- Rados Block Device - exposes block device like semantics on top of RADOS objects
- S3
- CephFS
- CVMFS

## MON, PM. Francisco Barros – Project Management and documentation

- [JIRA](https://indico.cern.ch/event/1580446/contributions/6661077/)
	- Issue type: task, sub-task, ...
	- Workflows
	- Priorities
	- Boards
	- Screens and Fields: options when you see your issues
	- Notifications
	- Integratiosn : Gitlab, SNOC, mattermost, https://cernforge.web.cern.ch/
- Documentation:
	- [Confluence](https://confluence.cern.ch/), very useful for intenral documentation and collaboration
		- JIRA, draw.io, sql, ...
	- Gitlab Pages

## TUE, AM. Francisco Barros – Modern Application Deployment & Deployment

- Images = read-only templates with app code, lib, dep
- Containers = runnable instances of images
- Container runtimes = runtimes manage containers and follow CRI
- Container registry
- Writing Dockerfiles best practices:
	- Latest shouldn't be used – can be prone to man-in-the-middle attack
	- Use [multi-stage](https://docs.docker.com/build/building/multi-stage/)
	- Docker ignore should be leveraged
	- Run as non-root
- Use ADD to COPY things, but we cannot use COPY to ADD something, COPY from image and ADD to pull
- Kaniko or [Buildah](https://buildah.io/) to build images in CI

## TUE, AM. Lorenzo Del Pianta, Vasvi Sharma – Creating and managing websites at CERN

- Wordpress: Request, configure, access, publish
- ACL: In app page>roles, you can define e-groups to have access to a specific page
- Pages and posts.
- Cover, layout blocks. Media and text vs columns
- Groups, patterns, import/export
- Analytics, matomo

## TUE, PM. Jose Castro Leon – Core compute services (part 1 of 2)

- [cern.ch/clouddocs](https://cern.ch/clouddocs)
- Change OS_REGION_NAME={cern|pdc}
- https://openstack.cern.ch/

## TUE, PM. Diana Gaponcic, Jack Charlie Munday – Introduction to registry.cern.ch and Kubernetes

- For each repo in registry.cern.ch, I have can 
- SBOM allows to see all dependencies/packages
- K8s

## TUE, PM. Alberto Pimpo – Deploying applications (part 1 of 2)

- OKD, PaaS, K8

## WED, AM. Antonio Delgado Peris, Panagiotis Gkonis – Core compute services (part 2 of 2)

- HTCondor is a batch system, schedules compute tasks. To run jobs.
- Input, executable and output
- Submit side (schedds) -> Broker (Central managers, a collector and a negoctiator) -> Execute side (worker nodes)
- Job translation: Submit file -> how to represent your job in a submit file?
- Every job has an ID : Job_ID = ClusterId.ProcID.
- When you submit, the start will depend on your share/priority
- By default Condor will transfer back to IFS every file in your output sandbox back to yyour submit directory, except if you mention `transfer_output_files = merge.out` or `= ""` if you do not want anything back
- You can access EOS for example.
- Be sure to test a single job first before submitting multiple jobs
- In lxplus: `myschedd show`, `condor_q`, `myschedd bump`, `condor_submit job.sub`
- If we want env vars, in submit part use Environment directive in the submit file.
- Debug tools: `condor_ssh_to_job {<jobid>|-auto-retry <jobid>}` or `condor_tail` 
- Schedd -> submit
- Condor for many small jobs, Slurm is for HPC
- Time: you must declare how much time your jobs need
- ClassAd : list of attributes about each job and each machine
- `condor_q 4910855.0 -af:h Cmd RequestCpus` to see Cmd and RequestCpus attributes
- Job matching : `condor_q -better <job_id> -machine slot1@<hostname>.cern.ch`
- File transfer: From job, you can transfer to EOS by using `xrdcp` cmd; declaring a `root://` URL; using an EosSubmit schedd

## WED, AM. Giacomo Tenaglia – Configuration & Infrastracture as Code

- Tech stack: OpenVox, Foreman, Gitlab, Terraform/OpenTofu
- Classifying nodes through Foreman
- This is on top of Openstack

## WED, PM. Andrzej Nowicki – Database Services (part 2 of 4) - DBoD maintenance exercises

## WED, PM. Pedro Miguel Esteves Maximino, Rodrigo Fernando Henriques Sobral, Diogo Castro – Data Analysis Techniques using SWAN and REANA (part 1 of 3)

## WED, PM.  Hannah Short – Authentication and authorization

- Based on Keycloak
- SAML connections to eduGAIN
- SAML only works for web services
- For SSO that live in web browser, they're gonna live in browser, client_ID, and safegard, adds a layer of security -> client secret
- ! Use OAuth refresh tokens. Expire sessions after 12 hours. 

## THU, AM. Raulian-Ionut Chiorescu – Services for Machine Learning applications (part 1 of 3)

- ML platform at CERN is based on Kubeflow.

## THU, AM. Hannes Jakob Hansen – Services for Machine Learning applications (part 2 of 3)

- Two approaches to Model training:
	- Single node: Useful for prototyping, smaller dt, models; limited by single node resources
	- Distributed training: scales across multiple nodes and multiple GPUs, suitable for large dt and models

## THU, AM. Andrzej Nowicki – Database Services (part 3 of 4) - Oracle Database

- Download SQL dev oracle client
- tnsnames.ora, download rpm file, so that it refreshes automatically
- Oracle is suitable for mission critical workloads
- DB links
- Data migrations, Data pump automation

## THU, PM. Amine Lahouel – Services for Machine Learning applications (part 3 of 3)

- Once a model is brewed, it needs to be served
- What is my input and what is my output, this is all we need to take care of, the serving is automatic

