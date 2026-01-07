✨ Fonctionnalités Implémentées
1. Écran de démarrage
Écran de démarrage avec le logo BookHub
Redirection automatique vers la page de connexion après 3 secondes
Configuration native pour Android, iOS et Web viaflutter_native_splash
2. Pages d'Authentification
Page de Connexion ( /connexion)
Design avec image de fond ( connexion.jpeg) et superposition transparente
Formulaire de connexion (email et mot de passe)
Boutons de connexion sociale avec dégradé violet :
Connexion via Google (icône)
Connexion via Twitter (icône)
Lien vers la page d'inscription
Page d'inscription ( /inscription)
Même design que la page de connexion pour la cohérence
Formulaire complet avec validation :
Nom complet
Courriel (avec validation)
Mot de passe (minimum 6 caractères)
Confirmation du mot de passe
Boutons de connexion sociale identiques à la page de connexion
Lien vers la page de connexion
3. Page d'Accueil ( /)
Affichage du logo de l'application ( app_icon.png)
Conception réactive (adaptative mobile/desktop)
Navigation vers les différentes sections
4. Autres pages
Articles ( /articles) : Catalogue de livres disponibles
Statistiques ( /stats) : Visualisation des données
Fermeture ( /fermeture) : Page de clôture avec vidéo
🛠️ Technologies & Packages Utilisés
Dépendances Principales
flutter: Cadre de développement
google_fonts: ^6.1.0: Intégration de la police Poppins
font_awesome_flutter: ^10.7.0: Icônes pour les réseaux sociaux (Google, Twitter)
video_player: ^2.8.1Lecture de vidéos
firebase_core: ^4.2.1Initialisation de Firebase
firebase_auth: ^6.1.2Authentification Firebase
cloud_firestore: ^6.1.0: Base de données Firestore
google_sign_in: ^6.1.6Connexion Google
provider: ^6.1.5+1: Gestion d'état
shared_preferences: ^2.2.2Stockage local persistant
Outils de Développement
flutter_native_splash: ^2.4.0: Génération du splash screen natif
flutter_launcher_icons: ^0.13.1: Génération des icônes d'application
📁 Structure du projet
lib/
├── main.dart                    # Point d'entrée de l'application
├── firebase_options.dart        # Configuration Firebase
├── controllers/
│   └── auth_controller.dart     # Contrôleur d'authentification
├── models/
│   └── user_model.dart          # Modèle de données utilisateur
├── providers/
│   └── auth_provider.dart       # Provider pour la gestion d'état auth
├── services/
│   └── auth_service.dart        # Service d'authentification Firebase
├── view/
│   ├── splash_screen_page.dart  # Écran de démarrage
│   ├── connexion_page.dart      # Page de connexion
│   ├── inscription_page.dart    # Page d'inscription
│   ├── accueil_page.dart        # Page d'accueil
│   ├── articles_page.dart       # Catalogue de livres
│   ├── stats_page.dart          # Statistiques
│   └── fermeture_page.dart      # Page de fermeture
└── widgets/
    └── navigation_bar.dart      # Barre de navigation personnalisée

assets/
├── icon/
│   ├── app_icon.png         # Icône de l'application
│   └── app_icon_bg.png      # Icône pour le splash screen
└── images/
    ├── connexion.jpeg       # Image de fond pour les pages d'auth
    ├── exemples.jpeg        # Images d'exemples
    └── couverture_*.jpeg    # Couvertures de livres
🚀 Installation et lancement
Prérequis
Kit de développement logiciel Flutter (>= 3.0.0)
Kit de développement logiciel Dart (>= 3.0.0)
Un émulateur ou un appareil physique
Installation
Cloner le projet (si applicable) ou naviguer dans le dossier
cd BookHub
Installer les dépendances
flutter pub get
Générer les icônes (si vous avez modifié app_icon.png)
dart run flutter_launcher_icons
Générer le splash screen (si nécessaire)
flutter pub run flutter_native_splash:create
Lancement
Pour lancer l'application :

flutter run
L'application démarre automatiquement sur l'écran de démarrage, puis redirige vers la page de connexion.

🎯 Points clés du design
Conception des Pages d'Authentification
Image de fond : Utilisation de connexion.jpegavec un overlay noir à 80% d'opacité pour améliorer la lisibilité
Cartes semi-transparentes : Formulaires dans des conteneurs blancs à 95% d'opacité avec ombres portées
Boutons sociaux : Design épuré avec uniquement les logos (FontAwesome), dégradé violet du clair vers le foncé
Bordures arrondies : Rayonne de 12px pour un aspect moderne
Conception réactive
Adaptation automatique pour mobile et ordinateur de bureau
Utilisation de LayoutBuilderpour détecter la taille de l'écran
Mise en page flexible avec ExpandedetFlex
📝 Notes importantes
Icônes de l'Application
L'icône principale est définie dansassets/icon/app_icon.png
Pour changer l'icône, remplacez le fichier et exécutez :
dart run flutter_launcher_icons
Les icônes natives sont générées automatiquement pour Android, iOS et Web
Navigation
Itinéraire initial : /splash(écran de démarrage)
Après le splash : redirection automatique vers/connexion
Toutes les routes sont définies dansmain.dart
Personnalisation
Les couleurs sont centralisées dans main.dartvia leThemeData
La police Poppins est appliquée globalement viafontFamily
Les styles de boutons sont définis danselevatedButtonTheme
🤝 Contribution
Ce projet est un travail de groupe. N'hésitez pas à :

Proposer des améliorations
Signaler des bugs
Partagez vos idées pour les prochaines fonctionnalités
📄 Licence
Ce projet est développé dans le cadre d'un travail universitaire.

🔐 Authentification
BookHub intègre un système d'authentification complet basé sur Firebase Authentication , offrant plusieurs méthodes de connexion pour une expérience utilisateur fluide.

Fournisseurs d'Authentification
L'application prend en charge trois méthodes d'authentification :

Email et Mot de Passe

Inscription avec validation des champs (nom complet, email, mot de passe)
Connexion classique avec email et mot de passe
Validation en temps réel des formulaires
Connexion Google

Authentification via Google Sign-In
Récupération automatique des informations utilisateur (nom, email)
Déconnexion préalable pour permettre le choix du compte
Connexion Twitter

Authentification via Twitter OAuth
Utilisation de TwitterAuthProviderFirebase
Gestion des erreurs spécifiques à Twitter
Persistance de la Connexion
L'application implémente une persistance de session utilisant SharedPreferences :

Sauvegarde automatique : Lors de la connexion réussie, l'état de connexion et les données utilisateur sont sauvegardées localement
Connexion persistante : L'utilisateur reste connecté même après la fermeture de l'application
Déconnexion explicite : Seule une déconnexion manuelle efface les données locales
Récupération des données : Les informations utilisateur sont rechargées depuis le stockage local au démarrage
Technique architecturale
AuthService : Service centralisé gérant toutes les opérations d'authentification
AuthProvider : Provider pour la gestion d'état global avecChangeNotifier
UserModel : Modèle de données utilisateur avec sérialisation JSON
Firebase Firestore : Stockage des données utilisateur dans la base de données
Sécurité
Gestion des erreurs Firebase avec messages traduits en français
Validation côté client des formulaires
Protection contre les attaques courantes (injection, etc.)
Déconnexion sécurisée effaçant toutes les données locales
