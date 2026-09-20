# Assignment-2: Linux VM-to-VM Network Connectivity

## Aim

To configure and establish network connectivity between two Linux Virtual Machines (VMs) using Oracle VirtualBox and verify communication between them using IP addresses and the `ping` command.

## Objectives

- Create two Linux Virtual Machines.
- Create the second VM either from scratch or by cloning an existing VM.
- Configure a separate NAT Network in VirtualBox.
- Connect both VMs to the same NAT Network.
- Check the IP address of both VMs.
- Test communication between the VMs using the `ping` command.
- Verify successful VM-to-VM network connectivity.

## Requirements

- Oracle VirtualBox
- Linux Virtual Machine
- Two VMs
- Internet/network connection
- Linux Terminal

---

# Procedure

## Step 1: Create the First Virtual Machine

1. Open **Oracle VirtualBox**.
2. Create a new Linux Virtual Machine.
3. Select the required Linux ISO image.
4. Configure the required RAM, CPU, and storage.
5. Complete the Linux installation.
6. Start the VM and make sure that the operating system is working properly.

---

## Step 2: Create the Second Virtual Machine

The second VM can be created in either of the following two ways.

### Method 1: Create the Second VM from Scratch

1. Open Oracle VirtualBox.
2. Click **New**.
3. Create another Linux VM.
4. Select the Linux ISO image.
5. Configure RAM, CPU, and storage.
6. Install Linux on the second VM.
7. Start the VM and verify that it is working correctly.

### Method 2: Create the Second VM by Cloning

Instead of installing Linux again, an existing VM can be cloned.

1. Shut down the first VM completely.
2. Open **Oracle VirtualBox**.
3. Select the existing Linux VM.
4. Right-click the VM and select **Clone**.
5. Give the new VM a different name, for example: Ubuntu VM-2

6. Select Full Clone.
7. When VirtualBox asks about MAC addresses, select:- Generate New MAC Addresses for All Network Adapters
   
8. Click Finish and wait for the cloning process to complete.
9. The newly created VM will appear in VirtualBox.

Important: When cloning a VM, a new MAC address should be generated for the cloned VM. This prevents both VMs from having the same network identity and helps avoid network connectivity problems.


Step 3: Start Both Virtual Machines
Start the first VM.
Start the second VM.
Wait until both Linux systems have completely booted.
Open the Terminal in both VMs.
Both VMs should now be running simultaneously.

Step 4: Create a NAT Network
A separate NAT Network is created manually so that both VMs can communicate with each other.

1. Open Oracle VirtualBox.
2. From the menu, open:- File → Tools → Network Manager
3. Open the NAT Networks section.
4. Click Create.
5. Enter a name for the NAT Network, for example:- MynatNetwork
apply the NAT Network configuration.
The NAT Network has now been created.

Step 5: Configure the Network Adapter of VM-1
1. Shut down VM-1 if necessary.
2. In VirtualBox, select VM-1.
3. Go to:- Settings → Network
4. Enable Adapter 1.
5. Under Attached to, select:- NAT Network
6. Select the NAT Network created earlier:- MynatNetwork
7. Click OK.

Step 6: Configure the Network Adapter of VM-2
1. Select VM-2 in VirtualBox.
2. Go to:- Settings → Network
3. Enable Adapter 1.
4. Under Attached to, select:- NAT Network
5. Select the same NAT Network:- MynatNetwork
6. Click OK.
Both VMs must be connected to the same NAT Network.

Step 7: Start Both VMs Again

Start both VMs after configuring their network adapters.
Open a Terminal in each VM.

Step 8: Check the IP Address of VM-1
In VM-1, open the Terminal and run:
ip addr
or: ip a
Find the IP address assigned to the network interface.
Example:
10.0.2.4

Note down the IP address of VM-1.


Step 9: Check the IP Address of VM-2
In VM-2, open the Terminal and run:
ip addr
or:
ip a
Find the IP address assigned to the network interface.
Example:
10.0.2.5
Note down the IP address of VM-2.
The exact IP addresses may be different depending on the DHCP configuration.

Step 10: Test Connectivity from VM-1 to VM-2
From VM-1, use the IP address of VM-2 with the ping command.
Example:
ping 10.0.2.5
If the connection is successful, replies similar to the following will be displayed:
64 bytes from 10.0.2.5: icmp_seq=1 ttl=64 time=0.XXX ms
64 bytes from 10.0.2.5: icmp_seq=2 ttl=64 time=0.XXX ms
Press:
Ctrl + C
to stop the ping test.


Step 11: Test Connectivity from VM-2 to VM-1
Now perform the reverse connectivity test.
From VM-2, use the IP address of VM-1:
ping 10.0.2.4
If successful, VM-2 will receive replies from VM-1.
Press:
Ctrl + C
to stop the test.


Step 12: Verify the Network Connectivity

The following points should be verified:

Both VMs are powered on.
Both VMs are connected to the same NAT Network.
Both VMs have different MAC addresses.
Both VMs have valid IP addresses.
VM-1 can ping VM-2.
VM-2 can ping VM-1.

Successful replies from the ping command confirm that communication between the two VMs has been established.
