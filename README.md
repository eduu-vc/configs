# 🏋️‍♂️ Infraestrutura Ximnasio - Configuracións

Este repositorio contén as configuracións, scripts e documentación técnica dos servizos empregados no proxecto de fin de ciclo do ciclo **ASIR**, destinado á infraestrutura TI dun ximnasio moderno e seguro.

## 🧠 Descrición xeral

O proxecto baséase na virtualización con **Proxmox VE** e nunha arquitectura segmentada en VLANs, que inclúe servizos como:

- Servidor de nomes interno (BIND9)
- Servidor DHCP (ISC-DHCP)
- Controlador de dominio con Samba 4 (AD/DC)
- NAS con OpenMediaVault
- Servidor web WordPress (na DMZ)
- Base de datos MariaDB
- Videovixilancia con ZoneMinder
- Emisión de radio con AzuraCast
- Cortalumes con pfSense
- Copias de seguridade e scripts automatizados

---

## 🗂️ Estrutura do repositorio

- 📁 **bind/** — DNS interno (zonas directas e inversas)
- 📁 **dhcp/** — Configuración do servidor ISC DHCP
- 📁 **samba/** — Samba AD: `smb.conf`, `krb5.conf`, scripts
- 📁 **mysql/** — Hostname e Network
- 📁 **BD/** — Modelo da base de datos (E/R, SQL)
- 📁 **omv/** — Exportacións Network, Hostname
- 📁 **wordpress/** — Apache, Let’s Encrypt, Fail2Ban, WP
- 📁 **pfsense/** — Regras de firewall exportadas
- 📁 **zoneminder/** — Exportacións Network, Hostname
- 📁 **azuracast/** — Exportacións Network, Hostname
- 🛠 **scripts/**
  - `backup_dns.sh` — Backup DNS
  - `backup_dhcp.sh` — Backup DHCP
  - `backup_samba.sh` — Backup Samba AD
  - `backup_mysql.sh` — Backup da base de datos
  - ` install_cli.sh` — Software Clientes

---

## 🛡️ Seguridade e separación de servizos

A arquitectura está segmentada do seguinte xeito:

| VLAN        | Función                            |
|-------------|-------------------------------------|
| VLAN10      | Administración e servizos internos |
| VLAN20      | Clientes WiFi                      |
| VLAN30      | Videovixilancia e control acceso   |
| VLAN100     | DMZ – Servidor web WordPress       |

---

## 🔐 Autenticación

A autenticación está centralizada mediante **Samba 4 como Active Directory**, co que se realiza o login nos equipos da rede

---

## 📦 Scripts útiles

Todos os scripts de backup fan:
- Compresión de ficheiros
- Subida automática ao repo de GitHub (privado)
- Uso de token personal (oculto vía `.env` no proxecto real)

---

## 📜 Licenza

Proxecto realizado para fins académicos por [@eduu-vc](https://github.com/eduu-vc) no marco do Ciclo Superior de Administración de Sistemas Informáticos en Rede (ASIR).  
Non destinado ao uso en produción sen revisión previa.

---

## 📧 Contacto

📨 eduveigacristobo22@gmail.com  
🐙 GitHub: [https://github.com/eduu-vc](https://github.com/eduu-vc)

---

🎓 **2024-2025**
