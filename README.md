# Shard Cluster - Network and Computing Play Cluster

## Hardware

Shard cluster ([cluster.shard](https://cluster.shard)) is a home built multi-purpose
cluster used for learning, testing and playing about with networks,
computing and other interesting technology.

It consists of the following:
    
- 1x [Raspberry PI 3 B+](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/) 1.4GHz
  - 128GB micro SD with raspbian image
- 1x TP-Link Gigabit Switch
- 3x [Odroid C4](https://www.odroid.co.uk/index.php?route=product/product&product_id=1027) 4GB 2GHz 64-bit quad-core
  - 3x 32GB eMMC modules with linux images

## Software

### DHCP and DNS

The raspberry pi is set up to act as a DHCP and a DNS server
as the cluster is intended to run as a separate network / subnet
away from general home networking.

The DHCP server used is the [isc-dhcp-server](https://www.isc.org/dhcp/)
as this felt the most configurable and interesting solution.

For DNS, [BIND-9](https://www.isc.org/bind/) is used, as it provides
a very flexible, full-featured DNS system.

## Ansible Playbook

### Dry run

To perform a dry-run,

```bash
$ ansible-playbook pave-shard-main.yml -i hosts -u martin --ask-pass --become --check
```

### Apply configuration

To apply the configuration,

```bash
$ ansible-playbook pave-shard-main.yml -i hosts -u martin --ask-pass --become
```
