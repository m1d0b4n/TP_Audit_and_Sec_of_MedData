```
.
├── Hyperviseur (Proxmox)
│   └── Noeud PVE
│       ├── VLAN Administration (10.0.1.0/24)
│       │   └── VM - Bastion (Debian)
│       │       └── IP : 10.0.1.2
│       │       └── Rôle : Point d'accès SSH sécurisé pour les administrateurs
│       │
│       ├── VLAN Applicatif (10.0.2.0/24)
│       │   └── VM - Serveur Nextcloud (CentOS)
│       │       └── IP : 10.0.2.10
│       │       └── Rôle : Serveur de stockage pour Nextcloud
│       │       └── Configuration : LVM + LUKS pour le chiffrement, RAID pour la redondance
│       │
│       ├── VLAN Bases de données (10.0.3.0/24)
│       │   └── VM - Serveur Base de données (MySQL)
│       │       └── IP : 10.0.3.10
│       │       └── Rôle : Base de données Nextcloud, accessible depuis le VLAN Applicatif
│       │       └── Configuration : Accès sécurisé avec ACLs et authentification forte
│       │
│       ├── VLAN Sauvegarde (10.0.4.0/24)
│       │   └── VM - Sauvegarde (Debian)
│       │       └── IP : 10.0.4.10
│       │       └── Rôle : Serveur de sauvegarde pour les VMs
│       │       └── Configuration : Snapshots et planification des sauvegardes
│       │
│       ├── VLAN Monitoring (10.0.5.0/24)
│       │   └── VM - Zabbix (Debian)
│       │       └── IP : 10.0.5.10
│       │       └── Rôle : Surveillance et monitoring de l'infrastructure
│       │       └── Configuration : Alertes et tableaux de bord
│       │
│       └── VLAN Utilisateurs (10.0.6.0/24)
│           └── Terminaux utilisateurs (Plage DHCP : 10.0.6.100 - 10.0.6.200)
│               └── Rôle : Accès utilisateur final avec restrictions d'accès
```
