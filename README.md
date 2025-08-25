flowchart TD
    A[Microsoft Forms] -->|Réponses| B[Flow 1 - Nouveau Formulaire]
    B -->|Insertion données| C[(Excel Online - OneDrive/SharePoint)]
    B -->|Email confirmation| D[Outlook - Répondant]

    C -->|Statut = En cours| E[Flow 2 - Relance planifiée]
    E -->|Envoi rappel| F[Outlook -> Expéditeur]
    F -->|Clique bouton/lien| G[Flow 3 - Mise à jour statut]
    G -->|Mise à jour Statut = Traité| C
