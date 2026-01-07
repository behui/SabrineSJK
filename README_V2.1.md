# 🌟 Sabrine SJK - Site de Thérapeute Énergétique V2.1

## 🎯 Vue d'Ensemble

Système complet de gestion pour thérapeute énergétique incluant :
- Site web public professionnel
- Espace client avec réservations
- Espace admin avec gestion complète (devis, factures, dépenses, trésorerie)
- Assistant IA pour publications
- Génération de PDF professionnels

---

## 📚 Documentation

### 🚀 Pour Bien Démarrer
1. **[QUICK_START.md](QUICK_START.md)** - ⚡ **COMMENCER ICI !**
   - Installation en 3 étapes
   - Premiers devis et factures
   - Utilisation de l'IA

2. **[CHANGELOG_V2.1.md](CHANGELOG_V2.1.md)** - 📋 Nouveautés V2.1
   - 9 fonctionnalités majeures
   - Guide détaillé de chaque feature
   - Exemples d'utilisation

### 📖 Guides Détaillés
3. **[GUIDE_GESTION.md](GUIDE_GESTION.md)** - 📊 Gestion d'entreprise
   - Workflow complet
   - Bonnes pratiques
   - Astuces comptables

4. **[GUIDE_PDF.md](GUIDE_PDF.md)** - 📄 Génération PDF
   - Format des documents
   - Personnalisation
   - Troubleshooting

---

## ⚡ Installation Express

### 1️⃣ Initialiser Firebase
```bash
# Ouvrir dans le navigateur
init-business.html

# Cliquer sur "Initialiser les Collections"
```

### 2️⃣ Se Connecter
```
Admin:
  Email: admin@sabrinesjk.fr
  Mot de passe: adminsabrinesjk
```

### 3️⃣ Configurer (IMPORTANT !)
```
1. Onglet "Personnalisation" (dernier)
2. Remplir TOUTES les informations société
3. Sauvegarder
```

**✨ Prêt à utiliser !**

---

## 🆕 Nouveautés V2.1

### 🤖 Assistant IA (Gratuit, Sans API)
```
📝 Publications → Assistant IA
💭 "Parlez du Reiki pour le stress"
⚡ Génération instantanée
✨ Texte professionnel avec emojis + hashtags
```

### 🎯 Auto-Remplissage
```
👤 Sélection Client → Email, Tél, Adresse remplis !
💰 Sélection Prestation → Prix + Description remplis !
```

### ⚙️ Personnalisation Complète
```
🏢 Infos société (SIRET, IBAN, Adresse...)
📄 Utilisation automatique dans TOUS les PDF
🎨 Mentions légales personnalisées
```

### 📅 Gestion Réservations
```
✓ Confirmer rapidement
✗ Annuler
🗑️ Supprimer
📊 Stats en temps réel
```

### 📄 PDF Pro
```
✅ Alignement parfait
✅ Données dynamiques
✅ Format A4 professionnel
✅ IBAN sur factures
```

---

## 🎨 Fonctionnalités Complètes

### 🏠 Site Public
- Page d'accueil moderne
- 4 services (Reiki, Lahochi, Magnétisme, Intuitif)
- Réservation en ligne
- Blog dynamique
- Responsive 100%

### 👤 Espace Client
- Profil personnalisable
- Historique réservations
- Calendrier disponibilités
- Réservation rapide

### 🔐 Espace Admin (9 Onglets)

#### 1. Dashboard
- Vue d'ensemble
- Stats générales

#### 2. Devis
- Création avec dropdowns
- Calculs automatiques
- PDF pro
- Stats (attente, acceptés, total)

#### 3. Factures
- Auto-remplissage
- Gestion paiements
- PDF avec IBAN
- Chiffre d'affaires

#### 4. Dépenses
- 8 catégories
- HT/TTC
- Stats mensuelles/annuelles

#### 5. Trésorerie
- Recettes vs Dépenses
- Solde temps réel
- Historique 20 mouvements

#### 6. Réservations ✨ NOUVEAU
- Liste complète
- Actions rapides
- Stats

#### 7. Publications
- Éditeur
- **IA gratuite** ✨
- Images
- Tags

#### 8. Personnalisation ✨ NOUVEAU
- Société
- Légal
- PDF

---

## 💡 Exemples d'Usage

### ⚡ Devis en 30 Secondes
```
1. Nouveau Devis
2. Client dropdown → Auto-fill
3. Prestation dropdown → Prix auto
4. Quantité
5. Save
6. PDF → Download
```

### 🤖 Article avec IA
```
1. Nouvelle Publication
2. IA: "lahochi élévation vibratoire"
3. Generate → 200+ mots
4. Image Unsplash
5. Publish
```

### 💰 Trésorerie
```
1. Onglet Trésorerie
2. Voir : Recettes | Dépenses | Solde
3. Historique
```

---

## 🔧 Stack Technique

- **Frontend** : HTML5, CSS3, JavaScript ES6+
- **Backend** : Firebase (Firestore + Auth)
- **PDF** : jsPDF + jsPDF-AutoTable
- **Calendrier** : FullCalendar
- **Icônes** : Font Awesome
- **IA** : Système local basé templates (gratuit)

---

## 📊 Architecture Firebase

```
Collections:
├── users           (clients + admin)
├── bookings        (réservations)
├── publications    (blog)
├── quotes          (devis)
├── invoices        (factures)
├── expenses        (dépenses)
└── settings        ✨ NOUVEAU
    └── company     (personnalisation)
```

---

## 🎨 Personnalisation

```css
/* Couleurs */
--primary: #8a2be2    /* Violet */
--secondary: #9333ea  /* Violet clair */

/* Polices */
--font-body: 'Poppins'
--font-heading: 'Playfair Display'
```

---

## ⚠️ Checklist Post-Installation

- [ ] ✅ Exécuter init-business.html
- [ ] ✅ Se connecter en admin
- [ ] ✅ Remplir Personnalisation (SIRET, IBAN...)
- [ ] ✅ Créer un devis test
- [ ] ✅ Générer un PDF test
- [ ] ✅ Vérifier alignement PDF
- [ ] ✅ Tester IA publications
- [ ] ✅ Tester dropdowns clients/prestations

---

## 🐛 FAQ

**Dropdowns vides ?**
→ Créez réservations/utilisateurs d'abord

**PDF sans mes infos ?**
→ Remplissez Personnalisation

**IA bizarre ?**
→ Mots-clés clairs : "reiki", "stress"...

**Erreur Firebase ?**
→ Vérif config dans indexV2.html

---

## 🚀 Roadmap

- [ ] Email automatique devis/factures
- [ ] QR code paiement
- [ ] Graphiques avancés
- [ ] Signature électronique
- [ ] Templates IA multiples
- [ ] Export CSV

---

## 📱 Responsive

✅ Mobile (< 768px)  
✅ Tablet (768-1024px)  
✅ Desktop (> 1024px)

---

## 📞 Contact

📧 contact@sabrinesjk.fr  
📱 06 12 34 56 78  
📍 Beauvoisin, Gard

---

## 🎉 Crédits

**Développé par** : GitHub Copilot  
**Version** : 2.1  
**Date** : 17 décembre 2025  
**Licence** : © 2025 Sabrine SJK

---

## 🚀 Démarrer Maintenant

### 👉 [Lire le Guide de Démarrage Rapide](QUICK_START.md)

---

**Enjoy! 🌟**
