# 📊 Architecture du projet : Microsoft Forms + Excel + Power Automate

## 🔎 Objectif
Mettre en place un système de collecte de données, suivi et relance automatique **sans Supabase, SMTP externe, Python ou Next.js**, entièrement basé sur Microsoft 365.

- Collecte des réponses via **Microsoft Forms**.
- Stockage dans un **fichier Excel Online** (OneDrive/SharePoint).
- Relance automatique par email pour les demandes **en cours**.
- Suivi du statut : **En cours → Traité**.

---

## 🏗️ Schéma d’architecture

```mermaid
flowchart TD
    A[Microsoft Forms] -->|Réponses| B[Flow 1 - Nouveau Formulaire]
    B -->|Insertion données| C[(Excel Online - OneDrive/SharePoint)]
    B -->|Email confirmation| D[Outlook - Répondant]

    C -->|Statut = En cours| E[Flow 2 - Relance planifiée]
    E -->|Envoi rappel| F[Outlook -> Expéditeur]
    F -->|Clique bouton/lien| G[Flow 3 - Mise à jour statut]
    G -->|Mise à jour Statut = Traité| C
```
