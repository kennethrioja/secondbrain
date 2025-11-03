# CERN School of Computing on IT Services 2025

## Sebastien Ponce – A bit of physics in a week of computing

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

## Andrzej Nowicki – DB Services (1/4), Intro to DB

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

## Abhishek Lekshamanan, Gianmaria Del Monte – Storage (part 1 of 2) and re-requisites

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

## Francisco Barros – Project Management and documentation

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

