# 🏢 Guide d'utilisation - Gestion d'Entreprise

## 📋 Vue d'ensemble

Ce système de gestion d'entreprise intégré permet de gérer complètement votre activité de thérapeute énergétique depuis l'espace administrateur.

---

## 🚀 Initialisation

### Étape 1 : Initialiser la base de données

1. Ouvrez le fichier **`init-business.html`** dans votre navigateur
2. Cliquez sur le bouton **"Initialiser les collections"**
3. Attendez la confirmation de succès

Cela créera les collections Firebase suivantes avec des exemples :
- ✅ **quotes** (devis)
- ✅ **invoices** (factures)
- ✅ **expenses** (dépenses)

---

## 📊 Fonctionnalités par onglet

### 1. Dashboard
Vue d'ensemble de votre activité :
- 📈 Nombre de réservations
- 👥 Nombre de clients
- 📊 Statistiques rapides
- 📅 Dernières réservations

### 2. Devis
Gestion complète des devis :

#### Créer un devis
1. Cliquez sur **"Nouveau Devis"**
2. Remplissez les informations :
   - **N° Devis** : Ex: DEV-2025-001
   - **Date** : Date d'émission
   - **Validité** : Nombre de jours (défaut: 30)
   - **Client** : Nom, email, téléphone, adresse
3. Ajoutez les prestations :
   - Description du service
   - Quantité
   - Prix HT
   - TVA (20%, 10%, 5.5%, 0%)
   - Cliquez sur "➕ Ajouter une ligne" pour plusieurs prestations
4. Les totaux se calculent automatiquement
5. Choisissez le statut :
   - 🟡 **Brouillon** : En cours de rédaction
   - 🔵 **Envoyé** : Envoyé au client
   - 🟢 **Accepté** : Client a accepté
   - 🔴 **Refusé** : Client a refusé
6. Cliquez sur **"Enregistrer"**

#### Statistiques affichées
- Devis en attente
- Devis acceptés
- Montant total des devis

### 3. Factures
Gestion des factures et paiements :

#### Créer une facture
1. Cliquez sur **"Nouvelle Facture"**
2. Remplissez :
   - **N° Facture** : Ex: FA-2025-001
   - **Date** : Date d'émission
   - **Échéance** : Date limite de paiement
   - **Client** : Coordonnées complètes
3. Ajoutez les prestations (même principe que devis)
4. Choisissez le statut de paiement :
   - 🟡 **Brouillon** : Non finalisée
   - 🔵 **Envoyée** : Envoyée au client
   - 🟢 **Payée** : Paiement reçu
   - 🔴 **En retard** : Échéance dépassée
   - ⚫ **Annulée** : Facture annulée
5. Cliquez sur **"Enregistrer"**

#### Statistiques affichées
- Factures impayées
- Factures payées
- Chiffre d'affaires total

### 4. Dépenses
Suivi de toutes vos dépenses professionnelles :

#### Ajouter une dépense
1. Cliquez sur **"Nouvelle Dépense"**
2. Remplissez :
   - **Date** : Date de la dépense
   - **Catégorie** : 
     - 📚 Formation
     - 🛠️ Matériel
     - 📢 Marketing
     - 💳 Abonnements
     - 🚗 Déplacements
     - 📦 Fournitures
     - 🛡️ Assurances
     - 📋 Autres
   - **Description** : Détail de la dépense
   - **Montant HT / TVA / TTC**
   - **Fournisseur** : Nom du fournisseur
   - **Notes** : Informations complémentaires
3. Cliquez sur **"Enregistrer"**

#### Statistiques affichées
- Dépenses du mois en cours
- Total annuel
- Catégorie la plus dépensée

### 5. Trésorerie
Vue d'ensemble financière :

#### Informations affichées
- 💰 **Recettes** : Total des factures payées
- 💸 **Dépenses** : Total des dépenses
- 💵 **Solde** : Recettes - Dépenses

#### Mouvements récents
- Liste des 20 derniers mouvements
- Détail : date, type, description, montant
- Couleur : vert pour recettes, rouge pour dépenses

### 6. Publications
Gestion du contenu du site (déjà fonctionnel)

---

## 💡 Bonnes pratiques

### Numérotation
- **Devis** : DEV-ANNÉE-XXX (Ex: DEV-2025-001)
- **Factures** : FA-ANNÉE-XXX (Ex: FA-2025-001)

### TVA
Pour les micro-entrepreneurs en franchise de TVA :
- Utilisez **TVA 0%** pour toutes les lignes
- Indiquez sur vos documents : "TVA non applicable, art. 293 B du CGI"

### Catégories de dépenses
Catégorisez systématiquement vos dépenses pour :
- Faciliter votre comptabilité
- Préparer vos déclarations fiscales
- Analyser vos coûts

### Sauvegarde
Firebase sauvegarde automatiquement toutes vos données. Vous pouvez :
- Consulter vos données depuis Firebase Console
- Exporter vos données si besoin

---

## 🔐 Accès Admin

**Email** : admin@sabrinesjk.fr  
**Mot de passe** : adminsabrinesjk

---

## 📱 Responsive

Toutes les fonctionnalités sont adaptées aux mobiles et tablettes.

---

## ⚡ Raccourcis clavier

- **Esc** : Fermer un modal
- **Entrée** : Valider un formulaire

---

## 🆘 Support

En cas de problème :
1. Vérifiez la console du navigateur (F12)
2. Vérifiez que Firebase est bien configuré
3. Vérifiez que toutes les collections existent

---

## 🎯 Prochaines améliorations possibles

- 📊 Graphiques de trésorerie
- 📧 Envoi automatique de devis/factures par email
- 📄 Génération PDF
- 📈 Statistiques avancées
- 🔔 Rappels automatiques pour factures impayées
- 📅 Intégration comptabilité

---

**Version** : 1.0  
**Date** : Décembre 2025
