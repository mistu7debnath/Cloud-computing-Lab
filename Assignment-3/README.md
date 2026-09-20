# Assignment-3: Creation of a Simple Network Topology Using Mininet

## Experiment

**Experiment 3: Creation of a Simple Network Topology Using Open-Source Network Virtualization Tools**

## Objective

To create and configure simple network topologies using Mininet, an open-source network virtualization tool, and verify communication between the virtual network nodes.

## Requirements

- Ubuntu Linux Virtual Machine
- Oracle VirtualBox
- Mininet
- Terminal

---

# Procedure

## Step 1: Start the Ubuntu Virtual Machine

1. Open **Oracle VirtualBox**.
2. Start the Ubuntu Linux Virtual Machine.
3. Log in to Ubuntu.
4. Open the Terminal.

---

## Step 2: Install Mininet

Mininet is installed using the Ubuntu package manager.

Run the following command:

```bash
sudo apt install mininet -y
```

Wait until the installation is completed.

The command installs Mininet along with its required dependencies.

---

## Step 3: Verify Mininet Installation

After installing Mininet, test the installation using:

```bash
 mn --version
```

This command creates a basic Mininet network and tests connectivity between the virtual hosts.

A successful result shows that the hosts can communicate with each other.

Example:

```text
*** Ping: testing ping reachability
h1 -> h2
h2 -> h1
*** Results: 0% dropped (2/2 received)
```

---

## Step 4: Create a Single-Switch Topology

To create a topology containing one switch and three hosts, use:

```bash
sudo mn --topo single,3
```

This creates a topology similar to:

```text
        s1
      / | \
    h1  h2  h3
```

Where:

- `s1` = Switch
- `h1` = Host 1
- `h2` = Host 2
- `h3` = Host 3

After running the command, the Mininet CLI appears:

```text
mininet>
```

---

## Step 5: Check the Links

Inside the Mininet CLI, run:

```bash
links
```

This displays the links between the hosts and the switch.

Example:

```text
h1-eth0<->s1-eth1
h2-eth0<->s1-eth2
h3-eth0<->s1-eth3
```

This verifies that the hosts are connected to the switch.

---

## Step 6: Test Connectivity

Inside the Mininet CLI, run:

```bash
pingall
```

The `pingall` command tests connectivity between all available hosts.

A successful test should show that there is no packet loss.

Example:

```text
*** Ping: testing ping reachability
h1 -> h2 h3
h2 -> h1 h3
h3 -> h1 h2

*** Results: 0% dropped
```

---

## Step 7: Create a Tree Topology

Mininet can also be used to create a hierarchical tree topology.

Run:

```bash
sudo mn --topo tree,3
```

This creates a tree topology with depth 3.

The topology contains multiple switches and hosts connected in a hierarchical structure.

A simplified representation is:

```text
              s1
            /    \
          s2      s3
        / | \    / | \
       h1 h2 h3 h4 h5 h6
```

---

## Step 8: Check the Tree Topology Links

After creating the tree topology, run:

```bash
links
```

This displays the connections between the hosts and switches.

The output can be used to verify that the topology has been created correctly.

---

## Step 9: Test the Tree Topology

Run:

```bash
pingall
```

This tests communication between all the hosts in the tree topology.

A successful result indicates that the virtual hosts can communicate through the switches.

---

## Step 10: Stop the Mininet Network

After completing the experiments, exit the Mininet CLI using:

```bash
exit
```

Mininet will stop the virtual network.

If required, the following command can be used to clean up the Mininet network:

```bash
sudo mn -c
```

---

# Commands Used

| Command | Purpose |
|---|---|
| `sudo apt install mininet -y` | Install Mininet |
| `sudo mn --test pingall` | Test basic Mininet connectivity |
| `sudo mn --topo single,3` | Create a single-switch topology with 3 hosts |
| `links` | Display network links |
| `pingall` | Test connectivity between all hosts |
| `sudo mn --topo tree,3` | Create a tree topology |
| `exit` | Exit the Mininet CLI |
| `sudo mn -c` | Clean up Mininet network components |

---

# Screenshots

## Screenshot 1 – Mininet Installation

Shows the installation of Mininet using:

```bash
sudo apt install mininet -y
```

## Screenshot 2 – Mininet Connectivity Test

Shows the result of:

```bash
sudo mn --test pingall
```

## Screenshot 3 – Single-Switch Topology

Shows the creation of:

```bash
sudo mn --topo single,3
```

## Screenshot 4 – Checking Links

Shows the output of:

```bash
links
```

for the single-switch topology.

## Screenshot 5 – Single-Switch Topology Diagram

Shows the graphical representation of the single-switch topology with multiple hosts.

## Screenshot 6 – Tree Topology

Shows the creation and structure of:

```bash
sudo mn --topo tree,3
```

## Screenshot 7 – Tree Topology Links

Shows the links between hosts and switches using:

```bash
links
```

## Screenshot 8 – Tree Topology Connectivity

Shows the connectivity test using:

```bash
pingall
```

---

# Result

The required network topologies were successfully created using Mininet. The links between the virtual hosts and switches were checked using the `links` command, and communication between the virtual hosts was verified using the `pingall` command.

# Conclusion

Thus, a simple network topology was successfully created and configured using the open-source network virtualization tool Mininet. Different topology structures were created, their links were examined, and connectivity between the virtual network nodes was verified successfully.
