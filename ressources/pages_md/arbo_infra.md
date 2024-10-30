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
│       │   └── VM - Server Nextcloud (CentOS)
│       │       └── IP : 10.0.2.10
│       │       └── Rôle : Serveur Nextcloud pour le stockage
│       │       └── Configuration : Connexion à la base de données dans le VLAN Bases de données
│       │
│       ├── VLAN Bases de données (10.0.3.0/24)
│       │   └── VM - Serveur Base de données (CentOS)
│       │       └── IP : 10.0.3.10
│       │       └── Rôle : Base de données Nextcloud, uniquement accessible depuis le serveur Nextcloud
│       │       └── Configuration : Accès limité aux requêtes de 10.0.2.10 via ACLs
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
