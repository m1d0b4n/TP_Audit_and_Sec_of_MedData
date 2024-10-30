```
.
├── Réseau
│   ├── Routeur de bordure
│   │   └── IP : 10.0.1.1
│   ├── Switch principal
│   │   └── IP : 10.0.1.3
│   ├── Pare-feu UTM (Sophos XG 115)
│   │   └── IP : 10.0.1.4
│   └── Point d’accès Wi-Fi
│       └── IP : 10.0.5.1
├── VLAN Administration (10.0.1.0/24)
│   ├── Serveur Bastion SSH
│   │   └── IP : 10.0.1.2
│   ├── Switch d’administration
│   │   └── Interface de gestion sécurisée
│   └── Gestion des ACLs
│       └── ACL pour restreindre les accès au VLAN Applicatif et Bases de données
├── VLAN Applicatif (10.0.2.0/24)
│   ├── Serveur Nextcloud
│   │   └── IP : 10.0.2.10
│   └── Serveur de fichiers (NAS Synology)
│       ├── IP : 10.0.2.11
│       ├── Chiffrement des données LVM + LUKS
│       └── Stockage RAID 6
├── VLAN Bases de données (10.0.3.0/24)
│   └── Serveur Base de données (MySQL)
│       ├── IP : 10.0.3.10
│       ├── Accès restreint depuis le VLAN Applicatif
│       └── Sauvegardes régulières sur NAS
├── VLAN DMZ (10.0.4.0/24)
│   └── Serveur Web public
│       ├── IP : 10.0.4.10
│       ├── HTTPS activé avec certificat SSL/TLS
│       └── Accès limité aux services HTTP/HTTPS depuis l’extérieur
└── VLAN Utilisateurs (10.0.5.0/24)
    ├── Point d’accès Wi-Fi
    │   └── IP : 10.0.5.1
    └── Plage DHCP pour terminaux employés
        ├── Plage IP : 10.0.5.100 - 10.0.5.200
        └── Accès restreint aux VLANs Applicatif et DMZ
```
