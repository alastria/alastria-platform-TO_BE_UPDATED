# Alastria Platform

* Release 1
	* Network Architecture
		* Overall network architecture
		* Throughput analysis
			* With different validator set sizes
			* With different block sizes
			* With different size of validator machines
		* Regular node technical requirements
			* Compute
				* CPU and memory requirements
			* Storage
				* Storage requirements
				* Checkpointing mechanism
			* Network
				* Network requirements
				* Ports and firewall considerations
		* Validator node technical requirements
			* Compute
				* CPU and memory requirements
			* Storage
				* Storage requirements
			* Network
				* Physical structure of validator network
				* Network requirements
				* Ports and firewall considerations
		* Number of Validator nodes
	* Installation and Configuration
		* Documentation on Github
		* Regular node
			* Node installation
			* Request inclusion
			* Verification that node works with network
				* At node level
				* At global network level
		* Validator node
			* Node installation
			* Request inclusion in Validator set
			* Verification that node works in network
				* At node level
				* At global network level
	* Network Monitoring
		* Approach to network monitoring
			* Cyber-security considerations
			* Performance considerations
			* Requirements on each node
		* Whole network
			* Dashboard
			* Detect violations of permissioning policy
			* Check network health
		* Validator set
			* Check validator set health
			* Check throughput
			* Detect validator node malfunctioning
		* Node
			* Geth
				* Get logs and metrics
				* Get TxPool status
			* Machine
				* Get versions of SW components of node
				* Get metrics (CPU, disk, network)
				* Update configuration files from repository
		* Self-update Monitor
	* Decentralized Network Administration (DNA)
		* Approach to network administration
			* Cyber-security considerations
			* Performance considerations
			* Requirements on each node
		* Whole network
			* Coordinate SW upgrade
			* Coordinate inclusion of a new Regular node
			* Coordinate exclusion of a Regular node
		* Validator set
			* Add new node to validator set
			* Remove a node from validator set
		* Regular Node
			* Restart Geth
			* Restart whole node
		* Validator node
			* Start/Stop/Update everything
	* Validator SLA compliance
		* Detection and notification of SLA violations
		* Excluding a failing Validator node
		* Re-inclusion of Validator node
	* Global incident management
* Release 2
	* Improve Permissioning mechanism
	* Improve Un-permissioning mechanism
	* Implement Validator Pool mechanism
	* Naming Service
* Policies
	* Selection policy of Validator nodes
	* Operating policy for a Validator node
	* Operating policy for a Regular node
