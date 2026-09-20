# Assignment-3: Creation of Network Topologies Using Mininet

## Experiment

**Experiment 3: Creation of a Simple Network Topology Using Open-Source Network Virtualization Tools**

## Objective

To create and configure different network topologies using Mininet and verify communication between the virtual network nodes.

## Requirements

- Ubuntu Linux Virtual Machine
- Oracle VirtualBox
- Mininet
- Terminal

---

# Step 1: Start Ubuntu Virtual Machine

1. Open **Oracle VirtualBox**.
2. Start the Ubuntu Linux Virtual Machine.
3. Open the Terminal.

---

# Step 2: Update Package Repository

Before installing Mininet, update the Ubuntu package repository:

```bash
sudo apt update
```

---

# Step 3: Install Mininet

Install Mininet using:

```bash
sudo apt install mininet -y
```

After the installation is completed, verify the Mininet version:

```bash
mn --version
```

This confirms that Mininet has been installed successfully.

---

# Step 4: Start Mininet

Start Mininet using:

```bash
sudo mn
```

The Mininet CLI will appear:

```text
mininet>
```

The `pingall` command can be used to verify whether the hosts are connected:

```bash
pingall
```

After completing the test, exit Mininet:

```bash
exit
```

Then clean the Mininet environment:

```bash
sudo mn -c
```

---

# Topology 1: Single Topology

## Step 5: Create Single Topology with 2 Hosts

Create a single-switch topology with two hosts:

```bash
sudo mn --topo single,2
```

The topology contains one switch and two hosts:

```text
        s1
       /  \
     h1    h2
```

Where:

- `s1` = Switch
- `h1` = Host 1
- `h2` = Host 2

---

## Step 6: View the Nodes

Inside the Mininet CLI:

```bash
nodes
```

This command displays all nodes present in the topology.

---

## Step 7: View the Links

Use:

```bash
links
```

This displays the connections between the hosts and the switch.

---

## Step 8: Check Host IP Address

To check the IP address of `h1`:

```bash
h1 ip addr
```

---

## Step 9: Test Communication Between Hosts

To test communication from `h1` to `h2`:

```bash
h1 ping -c 4 h2
```

This sends four packets from `h1` to `h2`.

Successful replies indicate that the hosts are connected.

---

## Step 10: Test All Hosts

Use:

```bash
pingall
```

This checks connectivity between all hosts in the topology.

---

## Step 11: Stop the Single Topology

Exit Mininet:

```bash
exit
```

Then clean the network:

```bash
sudo mn -c
```

---
