# Configuration EmailJS pour l'envoi d'emails

## Étape 1 : Créer un compte EmailJS

1. Allez sur https://www.emailjs.com/
2. Créez un compte gratuit (100 emails/mois inclus)
3. Confirmez votre email

## Étape 2 : Configurer le service email

1. Dans le dashboard EmailJS, allez dans "Email Services"
2. Cliquez sur "Add New Service"
3. Choisissez votre fournisseur (Gmail recommandé)
4. Connectez votre compte email (admin@sabrinesjk.fr)
5. Notez le **SERVICE_ID** généré (ex: service_xyz123)

## Étape 3 : Créer les templates d'emails

### Template 1 : Confirmation client (template_client_confirmation)

**Nom du template :** `template_client_confirmation`

**Sujet :** `Confirmation de votre réservation - Sabrine SJK`

**Contenu HTML :**
```html
<div style="font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; background-color: #f9f6f2;">
    <div style="background: white; padding: 30px; border-radius: 10px;">
        <h1 style="color: #8B7355; text-align: center;">✨ Confirmation de réservation</h1>
        
        <p>Bonjour {{to_name}},</p>
        
        <p>Votre demande de réservation a bien été enregistrée ! Je reviendrai vers vous très rapidement pour confirmer votre rendez-vous.</p>
        
        <div style="background: #f9f6f2; padding: 20px; border-radius: 8px; margin: 20px 0;">
            <h2 style="color: #8B7355; font-size: 1.2rem;">📋 Détails de votre réservation</h2>
            
            <p><strong>🌸 Prestation :</strong> {{service_name}}</p>
            <p><strong>📅 Date :</strong> {{booking_date}}</p>
            <p><strong>🕐 Heure :</strong> {{booking_time}}</p>
            <p><strong>📍 Lieu :</strong><br>{{location}}</p>
            
            <hr style="border: 1px solid #ddd; margin: 15px 0;">
            
            <p><strong>💰 Prix prestation :</strong> {{service_price}}</p>
            <p><strong>🚗 Frais déplacement :</strong> {{travel_cost}}</p>
            <h3 style="color: #8B7355;"><strong>Total TTC :</strong> {{total_ttc}}</h3>
        </div>
        
        <p><strong>Votre message :</strong><br>{{message}}</p>
        
        <p style="margin-top: 30px;">À très bientôt,<br>
        <strong>Sabrine</strong><br>
        Thérapeute Énergétique</p>
        
        <div style="text-align: center; margin-top: 30px; padding-top: 20px; border-top: 1px solid #ddd;">
            <p style="font-size: 0.9rem; color: #666;">
                📞 07 86 99 69 50<br>
                📧 admin@sabrinesjk.fr<br>
                📍 180 rue des mimosas, Beauvoisin
            </p>
        </div>
    </div>
</div>
```

**Variables du template :**
- `to_name` : Nom du client
- `service_name` : Nom de la prestation
- `booking_date` : Date du rdv
- `booking_time` : Heure du rdv
- `location` : Lieu (cabinet/domicile/distance)
- `service_price` : Prix de la prestation
- `travel_cost` : Frais de déplacement
- `total_ttc` : Total TTC
- `message` : Message du client

---

### Template 2 : Notification admin (template_admin_notification)

**Nom du template :** `template_admin_notification`

**Sujet :** `🔔 Nouvelle demande de réservation`

**Contenu HTML :**
```html
<div style="font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; background-color: #f0f0f0;">
    <div style="background: white; padding: 30px; border-radius: 10px;">
        <h1 style="color: #8B7355; text-align: center;">🔔 Nouvelle réservation</h1>
        
        <p>Une nouvelle demande de réservation vient d'être enregistrée sur le site.</p>
        
        <div style="background: #fff5f7; padding: 20px; border-radius: 8px; margin: 20px 0; border-left: 4px solid #ec4899;">
            <h2 style="color: #8B7355; font-size: 1.2rem;">👤 Client</h2>
            <p><strong>Nom :</strong> {{client_name}}</p>
            <p><strong>Email :</strong> {{client_email}}</p>
            <p><strong>Téléphone :</strong> {{client_phone}}</p>
        </div>
        
        <div style="background: #f9f6f2; padding: 20px; border-radius: 8px; margin: 20px 0;">
            <h2 style="color: #8B7355; font-size: 1.2rem;">📋 Réservation</h2>
            <p><strong>Prestation :</strong> {{service_name}}</p>
            <p><strong>Date :</strong> {{booking_date}}</p>
            <p><strong>Heure :</strong> {{booking_time}}</p>
            <p><strong>Lieu :</strong><br>{{location}}</p>
        </div>
        
        <div style="background: #e3f2fd; padding: 20px; border-radius: 8px; margin: 20px 0;">
            <h2 style="color: #8B7355; font-size: 1.2rem;">💰 Montants</h2>
            <p><strong>Prix prestation :</strong> {{service_price}}</p>
            <p><strong>Frais déplacement :</strong> {{travel_cost}}</p>
            <h3 style="color: #8B7355;"><strong>Total TTC :</strong> {{total_ttc}}</h3>
        </div>
        
        <div style="background: #f0f0f0; padding: 20px; border-radius: 8px; margin: 20px 0;">
            <h2 style="color: #8B7355; font-size: 1.2rem;">💬 Message du client</h2>
            <p style="font-style: italic;">{{message}}</p>
        </div>
        
        <div style="text-align: center; margin-top: 30px; padding: 20px; background: #8B7355; border-radius: 8px;">
            <p style="color: white; margin: 0;">
                <strong>Action requise :</strong> Contactez le client pour confirmer le rendez-vous
            </p>
        </div>
    </div>
</div>
```

**Variables du template :**
- `client_name` : Nom du client
- `client_email` : Email du client
- `client_phone` : Téléphone du client
- `service_name` : Nom de la prestation
- `booking_date` : Date du rdv
- `booking_time` : Heure du rdv
- `location` : Lieu
- `service_price` : Prix de la prestation
- `travel_cost` : Frais de déplacement
- `total_ttc` : Total TTC
- `message` : Message du client

## Étape 4 : Récupérer les clés API

1. Allez dans "Account" > "General"
2. Notez votre **PUBLIC KEY** (ex: xyz123abc456def789)

## Étape 5 : Modifier le code dans indexV2.html

Recherchez dans le fichier les lignes suivantes et remplacez :

1. **Ligne avec `emailjs.init("YOUR_PUBLIC_KEY")`**
   ```javascript
   emailjs.init("VOTRE_CLE_PUBLIQUE_ICI");
   ```

2. **Lignes avec `YOUR_SERVICE_ID`** (2 occurrences dans `confirmAndSendBooking`)
   ```javascript
   await emailjs.send('VOTRE_SERVICE_ID_ICI', 'template_client_confirmation', clientEmailParams);
   ```
   ```javascript
   await emailjs.send('VOTRE_SERVICE_ID_ICI', 'template_admin_notification', adminEmailParams);
   ```

## Étape 6 : Tester

1. Ouvrez votre site
2. Cliquez sur une prestation
3. Remplissez le formulaire
4. Cliquez sur "Voir le récapitulatif"
5. Vérifiez les détails
6. Cliquez sur "Confirmer et envoyer"
7. Vérifiez vos emails (client et admin)

## Limites du plan gratuit

- 100 emails/mois
- Si vous dépassez, passez au plan payant (15$/mois pour 1000 emails)

## Résolution de problèmes

### Les emails n'arrivent pas
- Vérifiez que les IDs sont corrects
- Vérifiez les noms des templates
- Vérifiez les variables dans les templates
- Vérifiez les spams
- Vérifiez les quotas EmailJS

### Erreur CORS
- EmailJS gère automatiquement CORS, pas de configuration nécessaire

### Email admin incorrect
- Modifiez la ligne dans `confirmAndSendBooking` :
  ```javascript
  to_email: 'VOTRE_EMAIL_ADMIN@example.com',
  ```
