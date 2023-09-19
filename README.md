
# Hadoop Cluster Setup on AWS EC2

This comprehensive guide will walk you through setting up a Hadoop cluster on Amazon Web Services (AWS) EC2 instances. The cluster comprises a Namenode, a Resource Manager, and multiple Datanodes, with additional coverage of SSH passwordless logins, essential cluster configurations, and Hadoop settings.

## Prerequisites

Before you begin, ensure you have the following prerequisites in place:

- An AWS account with sufficient permissions to create and manage EC2 instances.
- AWS CLI or access to the AWS Management Console.
- PuTTY (for Windows users) for SSH access to EC2 instances.

## Detailed Setup Steps

For a more detailed walkthrough of the setup process, follow the steps outlined in the [Hadoop Cluster Setup Guide](./Hadoop_Cluster_Setup_Guide.md).

## Quick Setup

If you're already familiar with the setup process, here's a quick-reference guide:

1. **Connect to the DataCenter**: Use SSH or PuTTY to connect to your EC2 instances using your private key.

2. **Update the System**: Execute system package updates using `sudo apt-get update && sudo apt-get dist-upgrade -y`.

3. **Configure SSH Key**: Copy your public key onto the DataCenter main server for SSH authentication.

4. **Create a Hadoop User**: Establish a dedicated 'hduser' for HDFS access with sudo privileges.

5. **Generate Local SSH Key**: Generate an SSH key pair for 'hduser' and add the public key to authorized_keys.

6. **Copy the Instance Public Key**: Transfer the instance's public key (`multi.pem`) to the 'hduser's' SSH directory.

7. **Install Java 8**: Install Java 8 (Open-JDK) using `sudo apt install openjdk-8-jdk openjdk-8-jre -y`.

8. **Download and Install Hadoop**: Download, extract, and install Hadoop.

9. **Set Environment Variables**: Configure environment variables for Hadoop.

10. **Update hadoop-env.sh**: Customize `hadoop-env.sh` for Java and log directory settings.

11. **Disable Firewall (iptables)**: Disable the firewall for seamless cluster communication.

12. **Disable Transparent Hugepage Compaction**: Configure Transparent Hugepage Compaction.

13. **Set Swappiness**: Set the swappiness value to 1.

14. **Configure NTP**: Set up NTP for time synchronization.

15. **Configure SSH Passwordless Logins**: Configure SSH for passwordless logins.

16. **Configure .profile**: Edit `.profile` to enable SSH agent forwarding.

17. **Create a Snapshot**: (Optional) Create a snapshot of the current instance for future use.

18. **Update /etc/hosts**: Update the `/etc/hosts` file with FQDNs for your cluster nodes.

19. **Install and Configure dsh**: Install and configure Distributed Shell (dsh) for node management.

20. **Configure Hadoop Masters and Slaves**: Update `masters` and `workers` files.

21. **Update core-site.xml**: Configure the default filesystem in `core-site.xml`.

22. **Update hdfs-site.xml**: Create directories and configure `hdfs-site.xml`.

23. **Create Directories on Datanodes**: Establish directories on Datanodes.

24. **Update yarn-site.xml**: Configure YARN settings in `yarn-site.xml`.

25. **Update mapred-site.xml**: Configure MapReduce settings in `mapred-site.xml`.

26. **Set Permissions**: Ensure proper permissions for Hadoop.

27. **SCP Configuration Files**: Copy configuration files to slave nodes using SCP.

28. **Format Namenode**: Format the Namenode.

29. **Start the Hadoop Cluster**: Initiate Hadoop services with `start-dfs.sh` and `start-yarn.sh`.

30. **Verify Installation**: Confirm the Hadoop installation by running a sample MapReduce job.

## Conclusion

Congratulations! You've successfully set up a Hadoop cluster on AWS EC2 instances, ready to harness Hadoop's power for distributed data processing and analysis.

For in-depth setup guidance with explanations and examples, please refer to the [Hadoop Cluster Setup Guide](./Hadoop_Cluster_Setup_Guide.md).

Happy Hadooping!
