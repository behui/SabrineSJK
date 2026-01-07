# 📄 Génération de PDF - Documentation

## ✅ Modifications effectuées

### 1. Redimensionnement des popups
Les modals business ont été optimisés pour une meilleure expérience :
- **Largeur** : 900px (au lieu de 1000px)
- **Hauteur max** : 90vh (au lieu de 95vh)
- **Padding** : 2rem pour plus d'espace interne
- **Scroll** : overflow-y auto pour les longs formulaires

### 2. Intégration jsPDF
Bibliothèques ajoutées dans l'en-tête HTML :
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf-autotable/3.5.31/jspdf.plugin.autotable.min.js"></script>
```

### 3. Fonction generateQuotePDF(id)
Génère un PDF professionnel pour les devis avec :

#### En-tête violet avec logo
- Nom "Sabrine SJK" en grand
- Sous-titre "Thérapeute Énergétique"
- Email de contact
- N° de devis en évidence à droite

#### Informations client
- Nom complet
- Adresse
- Email
- Téléphone

#### Tableau des prestations
Colonnes :
1. Description
2. Quantité
3. Prix HT
4. TVA %
5. Total HT

Style : lignes alternées (striped), en-tête violet

#### Section totaux
- Total HT
- TVA
- **Total TTC** (en gras, plus grand)

#### Conditions
- Validité du devis (30 jours par défaut)
- Modes de paiement
- Notes personnalisées si présentes

#### Pied de page
Mentions légales et SIRET

### 4. Fonction generateInvoicePDF(id)
Génère un PDF professionnel pour les factures avec :

#### Différences avec le devis
- Titre "FACTURE" au lieu de "DEVIS"
- Date d'échéance affichée
- **Badge "✓ PAYÉE"** en vert si facture payée
- Section "Facturé à" pour le client

#### Informations de paiement détaillées
- IBAN pour virement
- Possibilité espèces
- Chèque à l'ordre de...
- Date limite de paiement

#### Mentions légales renforcées
- TVA non applicable (article 293 B du CGI)
- Pénalités de retard

#### Mise en évidence du total TTC
Rectangle violet avec texte blanc pour le montant final

### 5. Boutons PDF dans les tableaux

#### Onglet Devis
Ajout d'un bouton <i class="fas fa-file-pdf"></i> **avant** les boutons Modifier/Supprimer
- Couleur rouge (#d32f2f) pour l'icône PDF
- Hover : rouge plus foncé (#b71c1c)
- Tooltip : "Générer PDF"

#### Onglet Factures
Même bouton PDF avec les mêmes caractéristiques

## 🎨 Format des PDF

### Couleurs utilisées
- **Violet primaire** : rgb(138, 43, 226) pour en-têtes
- **Gris foncé** : rgb(60, 60, 60) pour texte
- **Gris clair** : rgb(240, 240, 240) pour arrière-plans
- **Vert** : rgb(34, 139, 34) pour statut payé

### Typographie
- **Titres** : Helvetica Bold, 24pt (logo), 18pt (facture), 16pt (devis)
- **Sous-titres** : Helvetica Bold, 12pt
- **Texte** : Helvetica Normal, 10pt
- **Détails** : 9pt pour conditions, 8pt pour mentions légales

### Disposition
- **Marges** : 15mm à gauche, 10mm en haut du contenu
- **En-tête** : 40mm de hauteur avec fond violet
- **Tableau** : Commence à 95mm du haut
- **Totaux** : Alignés à droite, 65mm de largeur

### Éléments visuels
1. **Rectangle violet** : En-tête de page
2. **Rectangle gris clair** : Fond des totaux
3. **Rectangle violet** (factures) : Mise en évidence total TTC
4. **Lignes alternées** : Dans les tableaux
5. **Bordure** : Sous le titre du document

## 📋 Utilisation

### Pour générer un PDF de devis :
1. Aller dans l'onglet **Devis**
2. Cliquer sur l'icône <i class="fas fa-file-pdf"></i> rouge
3. Le PDF se télécharge automatiquement : `Devis_DEV-2025-001.pdf`

### Pour générer un PDF de facture :
1. Aller dans l'onglet **Factures**
2. Cliquer sur l'icône <i class="fas fa-file-pdf"></i> rouge
3. Le PDF se télécharge automatiquement : `Facture_FA-2025-001.pdf`

## ⚠️ Points importants

### SIRET à compléter
Dans le pied de page, remplacer `[À compléter]` par votre numéro SIRET réel :
```javascript
pdf.text('Sabrine SJK - Thérapeute Énergétique - SIRET: 123 456 789 00012', ...)
```

### IBAN à compléter
Dans la fonction `generateInvoicePDF`, ligne :
```javascript
pdf.text('- Virement bancaire: IBAN FR76 XXXX XXXX XXXX XXXX XXXX XXX', ...)
```
Remplacer par votre IBAN réel.

### TVA
Actuellement configuré pour micro-entrepreneur (TVA 0% par défaut).
La mention "TVA non applicable, article 293 B du CGI" est affichée.

### Notes personnalisées
Les champs `notes` des devis/factures sont affichés dans les PDF si renseignés.

## 🔧 Personnalisation

### Modifier les couleurs
Dans les fonctions, section "Configuration des couleurs" :
```javascript
const primaryColor = [138, 43, 226]; // Violet
const darkGray = [60, 60, 60];
const lightGray = [240, 240, 240];
```

### Modifier les coordonnées
Dans la section "En-tête" :
```javascript
pdf.text('Thérapeute Énergétique', 15, 27);
pdf.text('Email: contact@sabrinesjk.fr', 15, 33);
```

### Ajouter des champs
Utiliser les coordonnées (x, y) pour positionner :
```javascript
pdf.text('Nouveau texte', x, y);
```

## ✨ Fonctionnalités avancées

### Gestion multi-pages
jsPDF gère automatiquement les sauts de page si le contenu dépasse.

### Tableaux complexes
jsPDF-AutoTable permet :
- Colonnes de largeurs personnalisées
- Alignement (left, center, right)
- Styles par colonne
- En-têtes personnalisés

### Export
Les PDF sont générés côté client, pas besoin de serveur.

## 🎯 Prochaines améliorations possibles

- [ ] Ajouter logo/image en en-tête
- [ ] QR code pour paiement
- [ ] Signature électronique
- [ ] Envoi par email automatique
- [ ] Historique des PDF générés
- [ ] Templates personnalisables
- [ ] Watermark "BROUILLON" pour devis non envoyés
- [ ] Numérotation automatique des pages
- [ ] Conditions générales de vente complètes

---

**Version** : 1.0  
**Date** : 17 décembre 2024
