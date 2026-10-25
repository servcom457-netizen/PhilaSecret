# PhilaSecret — spécification produit

## Identité
Nom: PhilaSecret
Positionnement: messagerie privée et éphémère.
Slogan: « Votre message. Votre clé. Votre choix. »
Palette: Navy #071B3A, Cyan #00D8FF, Blanc #FFFFFF.

## Écrans
1. Splash / logo
2. Créer une identité
3. Accueil conversations
4. Nouvelle conversation
5. Chat
6. Visionneuse « Voir une fois »
7. Enregistrement audio
8. Sélecteur photo/vidéo
9. QR de vérification d'identité
10. Paramètres de confidentialité
11. Appareils liés
12. Informations de sécurité

## Règles éphémères
- `readOnce=true`: supprimer côté serveur dès confirmation de lecture.
- média view-once: clé de média séparée et suppression du fichier local après affichage.
- TTL optionnel: expiration serveur en complément, jamais comme seul mécanisme de confidentialité.
- l'utilisateur peut toujours conserver le contenu via un autre appareil/caméra; l'app ne peut pas empêcher physiquement cela.

## Modèle de menace
Le serveur est considéré comme honnête-mais-curieux: il relaie et stocke des blobs chiffrés mais ne doit pas avoir la clé privée de l'utilisateur.

## Production
Le protocole crypto doit être remplacé par une implémentation auditée de messagerie asynchrone avec ratchet, pré-clés, identité vérifiable, anti-rejeu, rotation, multi-appareils et groupes.
