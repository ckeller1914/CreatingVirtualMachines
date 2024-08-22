# CreatingVirtualMachines

##Task 1. Create a utility virtual machine

Create a VM

In the Cloud Console, on the Navigation menu (Navigation menu icon), click Compute Engine > VM instances.
Click Create Instance.

For Name, type a name for your instance. Hover over the question mark icon for advice about what constitutes a properly formed name.

For Region and Zone select us-east4 and us-east4-b respectively.

For Machine configuration, select Series as E2.

For Machine type, examine the options.

Click Details to the right of the Machine type list to see the breakdown of estimated costs.

For Machine type, click e2-standard-4 (4 vCPUs, 16 GB memory). How did the cost change?
For Machine type, click e2-medium (2 vCPUs, 4 GB memory).
For Boot disk, click Change.
Click Version and select Debian GNU/Linux 11 (bullseye) x86/64.
Click Select.
Click Advanced options.
Click Networking.
For Network interfaces, click the dropdown icon.
Select None for External IPv4 address.
Click Done.
Leave the remaining settings as their defaults, and click Create. Wait until the new VM is created.
Note: External IP addresses that don’t fall under the Free Tier of the Google Cloud Free Program will incur a small cost. Learn more about the pricing in the External IP address pricing section of the Virtual Private Cloud Guide.
Explore the VM details
On the VM instances page, click on the name of your VM.
Locate CPU platform and note the value. Click Edit.
Note: Notice that you cannot change the machine type, the CPU platform, or the zone.

You can add network tags and allow specific network traffic from the internet through firewalls. Some properties of a VM are integral to the VM, are established when the VM is created, and cannot be changed. Other properties can be edited.

You can add additional disks and you can also determine whether the boot disk is deleted when the instance is deleted.

Normally the boot disk defaults to being deleted automatically when the instance is deleted. But sometimes you will want to override this behavior. This feature is very important because you cannot create an image from a boot disk when it is attached to a running instance.

So you would need to disable Delete boot disk when instance is deleted to enable creating a system image from the boot disk.

Examine Availability policies.
Note: You cannot convert a non-preemptible instance into a preemptible one. This choice must be made at VM creation. A preemptible instance can be interrupted at any time and is available at a lower cost.

If a VM is stopped for any reason, (for example an outage or a hardware failure) the automatic restart feature will start it back up. Is this the behavior you want? Are your applications idempotent (written to handle a second startup properly)?

During host maintenance, the VM is set for live migration. However, you can have the VM terminated instead of migrated.

If you make changes, they can sometimes take several minutes to be implemented, especially if they involve networking changes like adding firewalls or changing the external IP.

Click Cancel.
Explore the VM logs
On the VM instance details page for your VM, click Logging.
Note: Notice that you have now navigated to the Logging page. This is a structured log view. At the top you can filter by using the pull-down menus, and there is a search box for searching based on labels or text.
Click the Expand this log entry icon to the left of one of the lines to see the kind of information it contains.
Click Check my progress to verify the objective.

Create a utility virtual machine
Task 2. Create a Windows virtual machine
Create a VM
On the Navigation menu (Navigation menu icon), click Compute Engine > VM instances.
Click Create instance.
Specify the following, and leave the remaining settings as their defaults:
Property	Value (type value or select option as specified)
Name	Type a name for your VM
Region	us-east4
Zone	us-east4-b
Series	E2
Machine type	e2-standard-2(2 vCPUs, 8 GB memory)
Boot disk	Change
Public Images > Operating system	Windows Server
Version	Windows Server 2016 Datacenter Core
Boot disk type	SSD persistent disk
Size (GB)	64
Click Select.
For Firewall, enable Allow HTTP traffic and Allow HTTPS traffic.
Click Create.
Note: When the VM is running, notice that the connection option in the far right column is RDP, not SSH. RDP is the Remote Desktop Protocol. You would need the RDP client installed on your local machine to connect to the Windows desktop.
Note: Installing an RDP client on your local machine is outside the scope of this lab and of the class. For this reason, you will not be connecting to the Windows VM during this lab. However, you will step through the usual procedures up to the point of requiring the RDP client. Instructions for connecting to Windows VMs are in the Connecting to Windows VMs Guide.
Set the password for the VM
Click on the name of your Windows VM to access the VM instance details.
You don't have a valid password for this Windows VM: you cannot log in to the Windows VM without a password. Click Set Windows password.
Click Set.
Copy the provided password, and click CLOSE.
Note: You will not connect to the Windows VM during this lab. However, the process would look something like the following (depending on the RDP client you installed). The RDP client shown can be installed for Chrome from the Chrome webstore. On the VM instances page, you would click RDP for your Windows VM and connect with the password copied earlier.
Click Check my progress to verify the objective.

Assessment Completed!
Create a Windows virtual machine
Assessment Completed!
Task 3. Create a custom virtual machine
Create a VM
On the Navigation menu (Navigation menu icon), click Compute Engine > VM instances.
Click Create instance.
Specify the following, and leave the remaining settings as their defaults an then click Select.
Property	Value (type value or select option as specified)
Name	Type a name for your VM
Region	us-east4
Zone	us-east4-b
Series	E2
Machine type	Custom
Cores	2 vCPU
Memory	4 GB
Boot disk	Debian GNU/Linux 11 (bullseye) x86/64
Click Create.
Connect via SSH to your custom VM
For the custom VM you just created, click SSH.
To see information about unused and used memory and swap space on your custom VM, run the following command:
free
Copied!
To see details about the RAM installed on your VM, run the following command:
sudo dmidecode -t 17
Copied!
To verify the number of processors, run the following command:
nproc
Copied!
To see details about the CPUs installed on your VM, run the following command:
lscpu
Copied!
To exit the SSH terminal, run the following command:
exit
Copied!
Click Check my progress to verify the objective.
