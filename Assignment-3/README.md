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
