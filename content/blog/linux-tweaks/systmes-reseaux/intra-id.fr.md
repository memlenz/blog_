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
Derrière ce jargon se cache une notion clé : **l’intégration des postes de travail dans l’annuaire d’entreprise**.  

Mais que signifie réellement cette opération ?  
Et surtout, quelle est la différence entre l’**Active Directory (AD classique)** et l’**Azure Active Directory (désormais Entra ID)** ?  

Cet article a pour objectif de clarifier ces points, avec une vision simple mais technique.

---

# Active Directory (AD) : l’annuaire historique

Active Directory (AD) est le système d’annuaire **on-premise** de Microsoft, utilisé depuis des décennies dans les entreprises.

- Les machines sont **jointes à un domaine** (ex. `entreprise.local`).
- Les utilisateurs s’authentifient avec un compte unique géré par l’IT.
- L’authentification repose sur des protocoles comme **Kerberos** et **NTLM**.
- L’IT applique des **politiques de groupe (GPO)**, déploie des logiciels et centralise la sécurité.

👉 En résumé : AD est le **cœur du réseau interne** de nombreuses entreprises.

---

# Azure Active Directory (Entra ID) : l’évolution cloud

Avec l’arrivée du cloud et du travail hybride, Microsoft a lancé **Azure Active Directory (Azure AD)**, désormais renommé **Entra ID**.

- 100% cloud, pas besoin de serveurs locaux.
- Gestion des identités pour **Office 365, Teams, SharePoint, applications SaaS, VPN**.
- Authentification moderne : **OAuth2, OpenID Connect, SAML**.
- Les machines peuvent être **jointes directement à Azure AD** ou fonctionner en **mode hybride** (via Azure AD Connect).

👉 En résumé : Entra ID étend la gestion des identités de l’entreprise **au cloud et aux applications SaaS**.

---

# "Mettre une machine sur l’intra ID" : concrètement

Dans le langage courant de l’entreprise, **mettre une machine sur l’intra ID** signifie :

1. **Intégrer la machine à l’annuaire** (AD local ou Azure AD).
2. **Permettre à l’utilisateur d’utiliser son compte entreprise** (plutôt qu’un compte local).
3. **Centraliser la gestion et la sécurité** du poste via l’IT.

Selon le contexte :

- 🔹 Si l’entreprise utilise un **AD interne** → la machine est intégrée au domaine classique.  
- 🔹 Si elle s’appuie sur le **cloud Microsoft** → la machine est rattachée à **Azure AD / Entra ID**.

---

# Vérifier l’appartenance d’une machine

### Sous Windows

- **Active Directory (AD local)** :  
  Aller dans *Paramètres > Système > Informations système* → *Domaine : entreprise.local*.  
- **Azure AD (Entra ID)** :  
  Aller dans *Paramètres > Comptes > Accès professionnel ou scolaire* → *Connecté à Azure AD*.  

### Sous Linux

- L’intégration se fait via des outils comme **SSSD, realmd ou Samba**.  
- Vérification avec :  

  ```bash
  realm list
  id utilisateur@entreprise.local

````

---

# Conclusion

👉 Mettre une machine sur l’**intra ID**, c’est en réalité **l’intégrer dans le système d’identité de l’entreprise**.

* Avec **Active Directory**, ce système est interne et local.
* Avec **Azure AD / Entra ID**, il s’ouvre vers le cloud et les applications modernes.

Pour les administrateurs systèmes et réseaux, comprendre cette distinction est essentiel pour anticiper la **transition du modèle on-premise vers le modèle cloud**.

---

# Pour aller plus loin

* [Documentation Microsoft sur Active Directory](https://learn.microsoft.com/fr-fr/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
* [Présentation d’Entra ID (Azure AD)](https://learn.microsoft.com/fr-fr/entra/fundamentals/whatis)
* [Différences AD vs Azure AD](https://learn.microsoft.com/fr-fr/azure/active-directory/fundamentals/active-directory-whatis)

```

---

## 🚀 Exemple de post LinkedIn relié à l’article  

> Quand je suis arrivé en entreprise, on m’a demandé de **"mettre des machines sur l’intra ID"**.  
>  
> Derrière cette expression se cache un sujet fondamental : **l’intégration des postes dans un annuaire d’entreprise**.  
>  
> 👉 Mais de quel annuaire parle-t-on ?  
> - **Active Directory classique (on-premise)** ?  
> - **Azure Active Directory (Entra ID)**, la version cloud ?  
>  
> J’ai écrit un article pour clarifier la différence, expliquer ce que cela change dans la gestion des machines, et montrer comment vérifier si une machine est jointe à AD ou Azure AD.  
>  
> 🔗 Lis l’article complet ici : [Lien vers ton blog]  
>  
> Et toi, ton entreprise est encore 100% AD ou déjà passée au cloud (Entra ID) ?  

---

