---
title: "Active Directory, Azure AD et Intra ID : comprendre l’intégration des machines"
date: 2025-09-25
tags: ["Active Directory", "Azure AD", "Entra ID", "Administration Système", "Sécurité"]
categories: ["Systèmes & Réseaux"]
description: "Qu’est-ce que signifie mettre une machine sur l’Intra ID ? Découvre la différence entre Active Directory et Azure AD (Entra ID), et comment les entreprises gèrent les identités et les postes de travail."
series: ["Systèmes & Réseaux"]
series_order: 0
---

# Introduction

En entreprise, on entend souvent des expressions comme **"mettre une machine sur l’intra ID"**.  
Derrière ce jargon se cache une question cruciale : **l’avenir de l’identité numérique des postes — restera-t-il on-premise avec Active Directory, ou migrera-t-il vers le cloud avec Entra ID ?**

Cet article a pour objectif de clarifier cette distinction, avec une vision simple mais technique.

---

# Active Directory (AD) : l’annuaire historique

Active Directory (AD) est le système d’annuaire **on-premise** de Microsoft, utilisé depuis plus de 20 ans dans les entreprises.

- Les machines sont **jointes à un domaine** (ex. `entreprise.local`).
- Les utilisateurs s’authentifient avec un compte unique géré par l’IT.
- L’authentification repose sur **Kerberos** et **NTLM**.
- L’IT applique des **politiques de groupe (GPO)**, déploie des logiciels et centralise la sécurité.

👉 En résumé : AD est le **cœur du réseau interne** de nombreuses entreprises.

---

# Azure Active Directory (Entra ID) : l’évolution cloud

Avec l’arrivée du cloud et du travail hybride, Microsoft a lancé **Azure Active Directory (Azure AD)**, désormais renommé **Entra ID**.

- 100% cloud, pas besoin de serveurs locaux.
- Gestion des identités pour **Office 365, Teams, SharePoint, applications SaaS, VPN**.
- Authentification moderne : **OAuth2, OpenID Connect, SAML**.
- Les machines peuvent être **jointes directement à Azure AD** ou fonctionner en **mode hybride** (via Azure AD Connect).
- Gestion de la sécurité moderne : **MFA, Conditional Access, Zero Trust**.

👉 En résumé : Entra ID étend la gestion des identités de l’entreprise **au cloud et aux applications SaaS**, avec une sécurité adaptée aux nouveaux usages.

---

# Comparatif AD vs Entra ID

| **Critère**          | **Active Directory (On-Premise)** | **Azure AD / Entra ID (Cloud)** |
|-----------------------|-----------------------------------|---------------------------------|
| Hébergement           | Serveurs locaux                  | Cloud Microsoft (Azure)         |
| Authentification      | Kerberos / NTLM                  | OAuth2, OIDC, SAML              |
| Gestion des machines  | Jointes au domaine interne        | Jointes au cloud / hybride      |
| Politiques (GPO)      | Oui (déploiement centralisé)      | Non (remplacé par Intune)       |
| Usage principal       | Réseau interne, PC fixes          | SaaS, travail hybride, BYOD     |
| Sécurité              | Classique, périmètre réseau       | MFA, Zero Trust, accès contextuel|
| système windows              | Tous les système windows       | A partir de windows 10|

---

# "Mettre une machine sur l’intra ID" : concrètement

Dans le langage courant, **mettre une machine sur l’intra ID** signifie :

1. **Intégrer la machine à l’annuaire** (AD local ou Azure AD).  
2. **Permettre à l’utilisateur d’utiliser son compte entreprise** (plutôt qu’un compte local).  
3. **Centraliser la gestion et la sécurité** du poste via l’IT.  

Selon le contexte :

- 🔹 Avec un **AD interne** → la machine est intégrée au domaine classique.  
- 🔹 Avec **Entra ID** → la machine est directement rattachée au cloud.

---

# Vérifier l’appartenance d’une machine

### Sous Windows

- **Active Directory (AD local)** :  
  Aller dans *Paramètres > Système > Informations système* → *Domaine : entreprise.local*.  

- **Azure AD (Entra ID)** :  
  Aller dans *Paramètres > Comptes > Accès professionnel ou scolaire* → *Connecté à Azure AD*.  

### Sous Linux

L’intégration Linux dans AD ou Entra est plus rare mais utile pour les serveurs.  
Elle se fait via **SSSD, realmd ou Samba**.  
Vérification avec :  

```bash
realm list
id utilisateur@entreprise.local
````

---

# Conclusion

👉 Mettre une machine sur l’**intra ID**, c’est en réalité **l’intégrer dans le système d’identité de l’entreprise**.

- Avec **Active Directory**, ce système est interne et local.
- Avec **Azure AD / Entra ID**, il s’ouvre vers le cloud et les applications modernes, avec une sécurité renforcée.

Pour les administrateurs systèmes et réseaux, comprendre cette distinction est essentiel pour accompagner la **transition du modèle on-premise vers le modèle cloud**.
Car le futur de la gestion des identités ne se joue plus seulement dans les salles serveurs, mais aussi dans le cloud.

---

# Pour aller plus loin

- [Documentation Microsoft sur Active Directory](https://learn.microsoft.com/fr-fr/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
- [Présentation d’Entra ID (Azure AD)](https://learn.microsoft.com/fr-fr/entra/fundamentals/whatis)
- [Différences AD vs Azure AD](https://learn.microsoft.com/fr-fr/azure/active-directory/fundamentals/active-directory-whatis)
