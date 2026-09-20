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
