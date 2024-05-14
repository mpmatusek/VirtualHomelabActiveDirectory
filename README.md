# Virtual Homelab w/ Active Directory
![image](https://github.com/mpmatusek/VirtualHomelabActiveDirectory/assets/167713753/075eed8a-36a2-4a4a-a860-927d6a7ac0cc)

## Setting up the Domain
<p>To enhance practical learning in cybersecurity, I embarked on creating a homelab equipped with Microsoft Active Directory and Domain Services. Opting for a virtualized approach as a starting point, I initiated the deployment within Oracle VirtualBox. A virtualized domain controller running Windows Server 2019 was the first cornerstone, meticulously configured to set the stage for the envisioned setup. Concurrently, I established three virtualized workstations, all running Windows 10, each equipped with private-facing network interface cards (NICs). This configuration necessitated connectivity to the domain controller prior to accessing the public internet. To facilitate this, the domain controller required the following components:</p>

<h2>Hardware</h2>
<ul>
  <li>Externally facing NIC</li>
  <li>Internally facing NIC</li>
</ul>

<h2>Active Directory and Domain Services</h2>
<ul>
  <li>FQDN: homelab.com</li>
  <li>Remote Access Service</li>
  <li>Network Address Translation</li>
  <li>Dynamic Host Configuration Protocol</li>
</ul>

<p>The DHCP server was set up with a static configuration, defining an IP range from 172.16.0.100 to 200, a subnet mask of 255.255.255.0, a gateway address of 172.16.0.1, and DNS at 175.16.0.1. This configuration enables workstations to access the public internet through the domain controller, which acts as a gateway, by obtaining addressing from the statically configured DHCP server.</p>

<p>To ensure smooth functionality, the internally facing NIC card was configured with the IP address 172.16.0.1 and a subnet mask of 255.255.255.0. However, the gateway field was left empty. Additionally, the loopback DNS was set to 127.0.0.1. This setup optimizes internal network communication while facilitating internet access for connected workstations.</p>
