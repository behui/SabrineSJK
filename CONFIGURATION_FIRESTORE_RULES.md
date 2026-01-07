# 🔥 Configuration des règles Firestore

## ❌ Problème : "Missing or insufficient permissions"

Vos règles Firestore bloquent l'accès en lecture/écriture.

## ✅ Solution : Modifier les règles Firestore

### Étape 1 : Accéder aux règles

1. Allez sur https://console.firebase.google.com/
2. Sélectionnez votre projet **sabrinesjk**
3. Dans le menu latéral : **Firestore Database**
4. Cliquez sur l'onglet **Rules** (Règles)

### Étape 2 : Choisir votre configuration

#### Option A : MODE DÉVELOPPEMENT (temporaire, pour tests)

**⚠️ ATTENTION : À utiliser UNIQUEMENT pour le développement/tests**

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

**Avantages :**
- ✅ Fonctionne immédiatement
- ✅ Pas besoin d'authentification pour tester

**Inconvénients :**
- ❌ Tout le monde peut lire/écrire vos données
- ❌ **NE PAS UTILISER EN PRODUCTION**

---

#### Option B : MODE PRODUCTION (recommandé)

**Règles sécurisées avec authentification :**

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    
    // Collections publiques en lecture, admin en écriture
    match /products/{product} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    
    match /publications/{publication} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    
    // Collections privées (admin uniquement)
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    
    match /bookings/{booking} {
      allow read: if request.auth != null;
      allow create: if true; // Permet aux clients de créer des réservations
      allow update, delete: if request.auth != null;
    }
    
    match /quotes/{quote} {
      allow read, write: if request.auth != null;
    }
    
    match /invoices/{invoice} {
      allow read, write: if request.auth != null;
    }
    
    match /expenses/{expense} {
      allow read, write: if request.auth != null;
    }
  }
}
```

**Avantages :**
- ✅ Sécurisé
- ✅ Clients peuvent réserver
- ✅ Admin peut tout gérer

**Inconvénients :**
- ⚠️ Il faut se connecter avec un compte admin pour initialiser

---

### Étape 3 : Publier les règles

1. Copiez les règles de votre choix (Option A pour débuter)
2. Collez-les dans l'éditeur Firebase Console
3. Cliquez sur **Publier** (Publish)
4. Attendez quelques secondes

### Étape 4 : Réessayer l'initialisation

1. Retournez sur [init-firebase.html](init-firebase.html)
2. Rechargez la page (F5)
3. Cliquez sur "🚀 Initialiser toutes les collections"

---

## 🔄 Migration vers la production

**Après vos tests, passez en mode production :**

1. Remplacez les règles par l'**Option B**
2. Créez un compte admin dans Firebase Authentication :
   - Firebase Console → Authentication → Users → Add user
   - Email : votre email
   - Mot de passe : votre mot de passe
3. Connectez-vous sur votre site avec ce compte
4. Toutes les opérations admin fonctionneront

---

## ⏱️ Règles temporaires (pour tests uniquement)

Si vous voulez tester rapidement, vous pouvez aussi créer des règles temporaires avec expiration :

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      // Expire le 15 janvier 2026 à minuit
      allow read, write: if request.time < timestamp.date(2026, 1, 15);
    }
  }
}
```

---

## 📞 Besoin d'aide ?

Si les erreurs persistent après avoir changé les règles :
1. Vérifiez que les règles sont bien publiées
2. Videz le cache du navigateur (Ctrl+Shift+Delete)
3. Rechargez la page d'initialisation
