# TP_Audit_and_Sec_of_MedData

## Scénario :
Vous êtes des administrateurs réseaux et sécurité travaillant pour une petite entreprise
de cybersécurité appelée SecureSys, spécialisée dans l’audit et la sécurisation des
systèmes d’information de ses clients. SecureSys a récemment décroché un contrat
pour moderniser et sécuriser l’infrastructure d’un client critique, MedData, une
société de stockage et d’analyse de données médicales.

<br>

## Aperçu du projet

![maquette](./ressources/images/maquette.png)

<br>

Il est préférable de cloner ce repo pour posséder directement l'intégralité des fichiers et pouvoir les consulter en local, commande :

```bash
git clone https://github.com/m1d0b4n/TP_Audit_and_Sec_of_MedData.git
```

<br>

## Table des matières

<details>
<summary>Arborescence de l'infrastructure réseau</summary>
<br>

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
</details>

<details>
<summary>Aperçu de l'interface PROXMOX</summary>
<br>

![image](./ressources/images/visu_proxmox.png)

</details>

<details>
<summary>Plan réseau Cisco Packet Tracer</summary>
<br>

</details>

<details>
<summary>Annuaire des utilisateurs, groupe et leurs rôles</summary>
<br>

| Groupe                  | Utilisateurs               | Rôle                                         | Accès                                                                                     |
|-------------------------|----------------------------|----------------------------------------------|-------------------------------------------------------------------------------------------|
| **Administrateurs**     | Rudy                       | Administrateur système                       | Accès complet au VLAN Administration, VLAN Applicatif, Sauvegarde, Bastion                |
|                         | Kevin                      | Administrateur réseau                        | Accès complet au VLAN Administration, configuration des routeurs et switches              |
|                         | Clément                    | Administrateur sécurité                      | Accès complet au VLAN Administration, gestion des pare-feux et politiques de sécurité     |
| **Médecins**            | Dr. Gregory House            | Médecin généraliste                          | Accès à Nextcloud, limité aux dossiers médicaux des patients                              |
|                         | Dr. Anna Tomie           | Médecin spécialiste                          | Accès à Nextcloud, accès restreint aux dossiers liés à son domaine                        |
| **Assistants médicaux** | Anne Tiseptique             | Assistante médicale                          | Accès à Nextcloud, accès restreint aux dossiers des patients pour mise à jour administrative |
| **Analystes de données**| Bill Athéral                | Analyste de données médicales                | Accès limité à Nextcloud pour les données et rapports, accès à Zabbix pour monitoring     |
| **Techniciens de maintenance** | Rémi Dié        | Technicien IT                                | Accès au serveur Bastion, équipements réseau et VLAN Administration pour support          |
| **R&D**                 | Dr. Patricia Ologie           | Chercheur principal                          | Accès aux dossiers de recherche dans Nextcloud, accès restreint aux données sensibles      |
| **RH et Administratif** | Vita Mine             | Responsable RH                               | Accès aux documents administratifs et RH dans Nextcloud                                   |
| **Comptabilité**        | Alex Pyration       | Comptable principal                          | Accès aux dossiers financiers dans Nextcloud                                              |
| **Internes et Stagiaires** | Emma Taume          | Interne                                      | Accès restreint dans Nextcloud, uniquement aux documents de formation                     |


</details>

<details>
<summary>Mise en place des 5 serveurs</summary>
<br>

<details>
<summary>SRV-NEXTCLOUD</summary>
<br>

</details>

</details>