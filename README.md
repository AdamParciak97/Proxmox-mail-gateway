# Proxmox-mail-gateway
Install and configuration connector e-mail

Download iso file from link --> 

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
