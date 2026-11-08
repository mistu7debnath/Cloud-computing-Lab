Assignment 4: Software Defined Networking (SDN)

Overview:
This assignment demonstrates the implementation of a Software Defined Networking (SDN) environment using Mininet, Open vSwitch (OVS), and the Ryu SDN Controller.

Objectives

Install and configure Mininet.

Install and configure Open vSwitch.

Set up the Ryu SDN Controller.

Create a virtual network topology.

Test communication between network hosts.

Monitor OpenFlow flow entries.

Implement packet filtering using a drop rule.


## Technologies Used
- Ubuntu 26.04 LTS
- Oracle VirtualBox
- Mininet
- Open vSwitch
- Ryu SDN Controller 4.34
- OpenFlow 1.3
- Python 3.9.25

## Network Topology

The experiment uses:
- One SDN controller (Ryu)
- One Open vSwitch (s1)
- Three hosts (h1, h2, h3)

```text
             Ryu Controller
                  (c0)
                   |
              OpenFlow 1.3
                   |
                Switch
                  s1
              /   |   \
             /    |    \
           h1     h2    h3
```

## Implementation

### 1. Update Ubuntu

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Mininet

```bash
sudo apt install mininet -y
```

### 3. Install Open vSwitch

```bash
sudo apt install openvswitch-switch -y
sudo systemctl status openvswitch-switch
```

### 4. Test Mininet

```bash
sudo mn
```

Inside Mininet:

```bash
nodes
pingall
exit
```

### 5. Set Up Python Environment

Install Python 3.9 using uv and create a virtual environment:

```bash
uv python install 3.9
uv venv --python 3.9 ryu39-env
source ryu39-env/bin/activate
```

Verify Python:

```bash
python --version
```

### 6. Install Ryu Controller

Clone the Ryu repository:

```bash
git clone https://github.com/faucetsdn/ryu.git
cd ryu
```

Install the required packaging dependencies:

```bash
uv pip install setuptools==67.6.1
uv pip install pbr
uv pip install wheel
```

Install Ryu:

```bash
uv pip install --no-build-isolation .
```

Verify installation:

```bash
ryu-manager --version
```

Expected output:

```text
ryu-manager 4.34
```

### 7. Start Ryu Controller

In the first terminal:

```bash
cd ~/Desktop/ryu
source ~/Desktop/ryu39-env/bin/activate
ryu-manager ryu.app.simple_switch_13
```

Keep the controller running.

### 8. Create Mininet Topology

Open a second terminal:

```bash
sudo mn --topo single,3 --controller=remote,ip=127.0.0.1,port=6633 --switch ovsk,protocols=OpenFlow13
```

Check network nodes:

```bash
nodes
```

Check network connections:

```bash
net
```

### 9. Test Host Connectivity

Inside the Mininet CLI:

```bash
pingall
```

Test individual host communication:

```bash
h1 ping h2
```

**Observed Output:**

```text
h1 -> h2 h3
h2 -> h1 h3
h3 -> h1 h2

*** Results: 0% dropped (6/6 received)
```

This confirms successful communication between all three hosts.

### 10. Display OpenFlow Flow Table

Open another Ubuntu terminal:

```bash
sudo ovs-ofctl -O OpenFlow13 dump-flows s1
```

This command displays the flow entries installed on the switch by the Ryu controller.

### 11. Add Drop Flow Rule

Execute:

```bash
sudo ovs-ofctl -O OpenFlow13 add-flow s1 "priority=100,in_port=1,actions=drop"
```

This rule instructs the switch to drop packets entering through port 1.

### 12. Test Packet Filtering

Return to the Mininet terminal:

```bash
h1 ping h2
```

The communication is expected to be blocked by the drop rule.

### 13. Delete Flow Rules

```bash
sudo ovs-ofctl -O OpenFlow13 del-flows s1
```

### 14. Clean Up Mininet

Exit Mininet:

```bash
exit
```

Clean up the network:

```bash
sudo mn -c
```

Stop the Ryu controller using `Ctrl + C` in its terminal.

## Results and Observations

The experiment demonstrated:

1. Successful installation of Mininet and Open vSwitch.
2. Successful installation and execution of Ryu Controller 4.34.
3. Creation of a virtual network with three hosts and one switch.
4. Successful communication between hosts with 0% packet loss.
5. Inspection of OpenFlow rules installed on the switch.
6. Configuration of a drop rule to demonstrate packet filtering.
7. Removal of flow entries and cleanup of the Mininet environment.

## Learning Outcomes

- Understanding SDN architecture.
- Understanding the role of a centralized SDN controller.
- Learning communication between Ryu and Open vSwitch.
- Creating virtual network topologies using Mininet.
- Understanding OpenFlow 1.3 and flow tables.
- Implementing basic network traffic filtering.

## Author

**Manisha Debnath**  
B.Tech – Computer Science and Engineering  
Adamas University

---

*Assignment 4 – Software Defined Networking (SDN)*
