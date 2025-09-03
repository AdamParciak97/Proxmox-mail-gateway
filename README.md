# Proxmox-mail-gateway
Install and configuration connector e-mail

Download iso file from link: 

```bash
https://www.proxmox.com/en/downloads/proxmox-mail-gateway/iso/proxmox-mail-gateway-8-2-iso-installer
```

### Architecture:
## CPU: 2 vCPU
## RAM: 4 GB
## Disk: 50 GB SSD

### Install proxmox mail gateway

### Choose Proxmox Mail gateway (graphical)
<img width="985" height="576" alt="image" src="https://github.com/user-attachments/assets/3a1ab4f2-4dfa-40fc-b3e2-08df687a9129" />

### Accept the license
<img width="1233" height="788" alt="image" src="https://github.com/user-attachments/assets/e46afb1a-3a6f-4af2-8d93-243f90137a9e" />

### Click next
<img width="1179" height="777" alt="image" src="https://github.com/user-attachments/assets/269fb56c-6903-4806-ba98-38a608179cc7" />

### Choose clock and time-zone
<img width="1169" height="784" alt="image" src="https://github.com/user-attachments/assets/539661eb-1a41-488d-8ea9-19b0f1c1e735" />

### Type password adminsitration
<img width="1234" height="789" alt="image" src="https://github.com/user-attachments/assets/6f27749f-5e5c-4a8e-b27f-e545d934424e" />

### Type IP-address, gateway, hostname
<img width="1174" height="782" alt="image" src="https://github.com/user-attachments/assets/3fa1f1bf-38b5-48f8-b976-ba7ea14b63a1" />

### Summary and install
<img width="1150" height="779" alt="image" src="https://github.com/user-attachments/assets/00918e11-d764-4e0d-ab2a-a760228901ea" />

### First logon to machine
```bash
https://192.168.10.177:8006
```

## Login: root
## Password: password entered during installation

### Configuration Relay Domains
Add all domains (test.pl, remote.pl ...)
<img width="886" height="303" alt="image" src="https://github.com/user-attachments/assets/8f4c546c-0003-4f12-838c-5518baf8252e" />

### Configuration transports
<img width="1079" height="306" alt="image" src="https://github.com/user-attachments/assets/b9128474-1328-4532-aba3-3330c0d159a2" />

### We have ready machine PMG to integration with Exchange from Relay domains and transports

### Optional settings
<img width="396" height="368" alt="image" src="https://github.com/user-attachments/assets/9f21eae9-1f91-44d4-a2cc-ac6257c3643b" />

<img width="376" height="323" alt="image" src="https://github.com/user-attachments/assets/9979acba-daa4-4641-b9d9-60ae9f2edb00" />

### Configuration LDAP
<img width="704" height="394" alt="image" src="https://github.com/user-attachments/assets/62091e63-c1e5-4408-bf29-593d83fd900f" />

### Create local backup PMG
<img width="929" height="497" alt="image" src="https://github.com/user-attachments/assets/30c2da4f-a754-4126-b66c-737618546382" />

### Create certificates via open-ssh and upload key and chain certificates

### Create file reqsan.cnf. Add IP, Common name, Location, State, Country, Organization, Organization Unit
<img width="527" height="613" alt="image" src="https://github.com/user-attachments/assets/ba0ad49b-60ed-4e8a-a45d-2834d56df918" />

### Create CSR and private key file
```bash
openssl req -new -newkey rsa:4096 -sha384 -nodes -keyout mx01.key -out mx01.csr -config reqsan.cnf -reqexts v3_req
```

### Check csr file
```bash
openssl req -in mx01.csr -noout -text
```

<img width="611" height="674" alt="image" src="https://github.com/user-attachments/assets/13726580-cee2-47a2-9cf7-893e9e6172ce" />

### Import private key and chain certificate
<img width="1257" height="692" alt="image" src="https://github.com/user-attachments/assets/298e3d61-2a14-49eb-b6bd-aec7f804ea1b" />

### We can configure proxy and edit administration e-mail 
<img width="576" height="311" alt="image" src="https://github.com/user-attachments/assets/36c4c213-de10-4740-b4e5-96d9afd71d87" />

### Configure syslog to SIEM
## Login via SSH to SERVER
## Modify file rsyslog.conf or install filebeat rpm
<img width="211" height="44" alt="image" src="https://github.com/user-attachments/assets/766cdc99-9edc-4ef9-a9a6-d79d0e6f1b99" />

### Paths worth analyzing in SIEM

```bash
/var/log/syslog – system logs + postfix (mail flow);
/var/log/pmgproxy/pmgproxy.log – GUI/API logs;
/var/log/pmgdaemon/pmgdaemon.log – PMG daemon logs;
/var/log/clamav/ – antivirus logs;
/var/log/spamassassin/ – antispam logs
```
### Create CLUSTER PMG

## Create other machine with PMG
## Click Create 

<img width="1409" height="400" alt="image" src="https://github.com/user-attachments/assets/a68edf3b-2bb5-46ca-8030-391e9ddae03a" />

### Join to Cluster PMG

## We must click add to other machine and enter the IP address and the generated token

<img width="783" height="145" alt="image" src="https://github.com/user-attachments/assets/692f5611-65dc-4a6a-87fb-d6671f1d1c57" />


### Final configuration - rules
We can control and modify rules. We also add new rules to control flows.
<img width="1920" height="756" alt="image" src="https://github.com/user-attachments/assets/b98d0558-5a4f-48d5-b935-b31aa67c9809" />
