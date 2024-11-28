# Cahier des charges techniques

## I - Introduction

### **A. Présentation du Projet**

**SMASH HERE** est une plateforme e-sport spécialisée dans les jeux de combat, destinée à centraliser et structurer l’apprentissage et la progression des joueurs. Elle repose sur des **roadmaps interactives et personnalisées**, conçues pour guider les joueurs à travers des étapes clés de progression, adaptées à leur niveau (débutant, intermédiaire, avancé) et à leurs besoins spécifiques (jeu, personnage, stratégie).
Les roadmaps sont des guides qui décrive les étapes à suivre pour arriver à un objectif.

Ces roadmaps sont conçues pour :

- **Centraliser l’information** aujourd’hui dispersée sur différentes plateformes ([YouTube](https://www.youtube.com), [X](https://www.x.com), [Reddit](https://www.reddit.com), [Discord](https://www.discord.com), [Twitch](https://www.twitch.com)).
- **Simplifier l’apprentissage** grâce à des parcours interactifs et évolutifs.
- **Offrir des outils de suivi personnalisés** pour optimiser les simplifier et accélérer l'apprentissage.
- **Fédérer une communauté active**, tout en proposant des solutions adaptées aux besoins de chaque utilisateur.

**Missions principales** :

- **Centralisation des ressources** : Regrouper et valider les informations pour éviter la dispersion.
- **Apprentissage structuré** : Proposer des parcours pédagogiques clairs et interactifs.
- **Personnalisation de l’expérience utilisateur** : Offrir des outils de suivi et d’ajustement des roadmaps.
- **Engagement communautaire** : Créer un espace collaboratif pour les joueurs et les coachs.

### B. Contexte et objectifs

#### 1. Contexte

La **Fighting Game Community (FGC)** est la communauté des jeux de combat. C'est une communauté dynamique cependant confrontée à un problème récurrent : **l’éparpillement des ressources**, la recherche chronophage d’informations fiables, et un **manque d’outils structurés** pour optimiser la progression des joueurs. Ces contraintes freinent non seulement les amateurs mais aussi les joueurs compétitifs souhaitant s'améliorer efficacement.

#### 2. Objectifs

- **Marché ciblé** : La plateforme cible principalement les joueurs de jeux de combat (débutants, intermédiaires, professionnels) et les coachs e-sportifs. Les créateurs de contenu forment une cible secondaire.
- **Concurrence** : Bien que des alternatives existent (YouTube, [Metafy](https://www.metafy.com), [Dash Fight](https://dashfight.com/)), aucune ne propose une approche centralisée, interactive et personnalisée comme **SMASH HERE**.
- **Besoins identifiés** :
    - Progresser grâce à des contenus structurés et adaptés.
    - Accéder facilement à des ressources validées.
    - Collaborer avec des "experts" du milieu (joueurs pro) pour un apprentissage avancé.
- **Moyens existants** : Actuellement, les joueurs s’appuient sur des tutoriels vidéos, des forums, ou des sessions de coaching payantes, souvent coûteuses.
- **Résultats attendus** : Une adoption rapide par la communauté grâce à l’intuitivité de la plateforme et à sa capacité à combler les lacunes actuelles.
- **Délais** : Livraison d’une version MVP fin Juillet, avec un développement agile pour intégrer de nouvelles fonctionnalités.

### C. Contraintes du Projet

#### 1. Contraintes techniques

1. **Infrastructure** : Nécessité d’un backend bien organisé pour gérer les roadmaps et leur contenu.
2. **Sécurité** : Conformité RGPD et sécurisation des données personnelles.
3. **Accessibilité multiplateforme** : Expérience fluide sur **iOS**, **Android**, et **Web**.
4. **Technologies utilisées** :
    - **Frontend** : SvelteJS pour une interface rapide et réactive.
    - **Backend** : Golang pour gérer des interactions complexes et sa rapidité d'éxécution.
    - **Base de données** : MongoDB pour sa flexibilité des données.

#### 2. Contraintes économiques

1. Développement sur plusieurs plateformes nécessitant des ressources importantes et un coût élevé tant de dévelopement que de maintien.
2. Achat de licences iOS (99€/an) et MacOS pour les tests et la publication côté Apple.
3. Maintenance des serveurs et coûts d’hébergement.

#### 3. Contraintes organisationnelles

- Dépendance envers les coachs et créateurs de contenu pour enrichir les ressources.
- Coordination avec des joueurs professionnels pour valider les contenus.
- Gestion communautaire pour garantir la qualité et la pertinence des informations.

## II - Les Fonctionnalités

Les fonctionnalités de l'application sont centrées autour des roadmaps. Ces fonctionnalités sont pensées pour simplifier l’apprentissage des joueurs et offrir une expérience personnalisée. Nous les avons regroupées par type d’utilisateur.

### A. Description détaillée et spécifications techniques

#### 1 - Roadmaps

- Description : Parcours structurés couvrant les concepts généraux et spécifiques des jeux de combat.
- Exigences fonctionnelles :
    - Personnalisation par utilisateur.
    - Suivi en temps réel des progrès (suivi de progression en pourcentage).
    - Intégration de contenus multimédias (vidéos, quiz).

**Tableau technique**

|Fonctionnalité|Description|Étapes|Cas d’erreur|
|---|---|---|---|
|Suivi de progression|L’utilisateur marque les étapes de la roadmap comme "validé", "en cours", ou "non commencé".|1. L’utilisateur sélectionne une roadmap. 2. Navigue dans les étapes. 3. Marque une étape selon son statut.|- Perte de connexion. - Problème serveur lors de l’enregistrement de l’état.|
|Ajout aux favoris|Permet de sauvegarder une roadmap pour un accès rapide depuis le tableau de bord.|1. L’utilisateur sélectionne une roadmap. 2. Clique sur "Ajouter aux favoris".|- Roadmap déjà ajoutée aux favoris. - Erreur d’ajout en base de données.|
|Création de roadmap (coach)|Les coachs peuvent créer une roadmap avec des étapes personnalisées et du contenu multimédia (vidéos, quiz, descriptions).|1. Le coach accède au formulaire de création. 2. Ajoute des étapes. 3. Associe des contenus multimédia. 4. Publie la roadmap.|- Erreur dans le téléchargement des contenus. - Étape obligatoire non renseignée.|

#### 2 - Utilisateurs

**Pour les joueurs**

- Création de compte avec pseudonyme, email ou connexion via Twitter/X.
- Suivi des roadmaps :
    - Ajout aux favoris.
    - Suivi de la progression avec des indicateurs (statuts : "validé", "en cours").
- Interaction communautaire :
    - Commentaires et notations des roadmaps.
    - Partage des progrès sur les réseaux sociaux.
- Personnalisation du profil : Image, pseudonyme, gestion des données.

**Tableau technique :**

|Fonctionnalité|Description|Étapes|Cas d’erreur|
|---|---|---|---|
|Création de compte|Permet à un utilisateur de créer un compte en fournissant un pseudonyme, un email, et un mot de passe ou via Twitter/X.|1. L’utilisateur remplit le formulaire. 2. Validation des données. 3. Enregistrement en base de données.|- Email déjà utilisé. - Pseudonyme déjà pris. - Mot de passe non conforme (longueur, caractères spéciaux manquants).|
|Connexion|L’utilisateur se connecte à son compte avec son pseudonyme ou email et son mot de passe.|1. L’utilisateur remplit ses identifiants. 2. Vérification des informations. 3. Validation et connexion à la session utilisateur.|- Identifiants incorrects. - Compte inexistant. - Problème serveur.|
|Suppression de compte|Supprime définitivement les données associées au compte de l’utilisateur.|1. L’utilisateur accède à la section "Suppression de compte". 2. Confirmation de la suppression. 3. Suppression des données dans la base de données.|- Confirmation non validée. - Problème serveur.|
|Modification de profil|Permet à l’utilisateur de mettre à jour son pseudonyme, mot de passe, ou photo de profil.|1. L’utilisateur accède à son profil. 2. Modifie les champs désirés. 3. Validation des modifications.|- Erreur serveur. - Champs obligatoires non remplis.|

**Pour les coachs**

- Création et gestion de roadmaps.
- Partage et publication de roadmaps :
    - Public ou privé (réservé à certains utilisateurs).
- Suivi des élèves (joueurs) :
    - Visualisation des progrès.
    - Feedback sur les étapes validées.
    - Gestion des paiements via Stripe/PayPal.
- Monétisation : Abonnement pour avoir accès à certaines roadmaps et/ou roadmaps payantes des coachs.
- Exigences non fonctionnelles :
    - Sécurisation des transactions financières.

**Tableau technique**

| **Fonctionnalité**                  | **Description**                                                                                      | **Étapes**                                                                                                                                                                                                                   | **Cas d’erreur**                                                                                                            |
|-------------------------------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **Création de compte**              | Permet aux coachs de s'inscrire en fournissant un pseudonyme, un email, et un mot de passe ou via Twitter/X. | 1. Le coach remplit le formulaire d’inscription.<br>2. Validation des données.<br>3. Enregistrement dans la base de données.<br>4. Connexion automatique après création de compte.                                             | - Email déjà utilisé.<br>- Pseudonyme déjà pris.<br>- Mot de passe non conforme (longueur, caractères spéciaux manquants).   |
| **Connexion**                       | Permet aux coachs de se connecter pour gérer leurs roadmaps et leur profil.                          | 1. Le coach entre ses identifiants.<br>2. Vérification des informations.<br>3. Accès au tableau de bord personnel.                                                                   | - Identifiants incorrects.<br>- Compte inexistant.<br>- Problème serveur.                                                  |
| **Création de roadmaps**            | Les coachs peuvent créer des roadmaps avec des étapes, vidéos, quiz et descriptions personnalisées.   | 1. Le coach accède à l’éditeur de roadmaps.<br>2. Définit le titre et les étapes de la roadmap.<br>3. Ajoute du contenu multimédia.<br>4. Valide et publie la roadmap.                                                       | - Problème de téléchargement des fichiers multimédias.<br>- Étape obligatoire manquante.<br>- Problème de publication.      |
| **Modification de roadmaps**        | Permet de modifier une roadmap existante, ajouter ou supprimer des étapes ou des contenus multimédias. | 1. Le coach sélectionne une roadmap depuis son tableau de bord.<br>2. Accède à l’éditeur.<br>3. Modifie les éléments souhaités.<br>4. Enregistre les modifications.                                                          | - Problème d’enregistrement.<br>- Conflit entre versions.<br>- Erreur de chargement des contenus modifiés.                  |
| **Suppression de roadmaps**         | Supprime définitivement une roadmap du compte du coach.                                              | 1. Le coach sélectionne une roadmap à supprimer.<br>2. Confirme la suppression.<br>3. La roadmap est supprimée de la base de données.                                                 | - Suppression accidentelle sans confirmation.<br>- Problème serveur.                                                       |
| **Partage de roadmaps**             | Les coachs peuvent partager une roadmap en public ou la restreindre à des utilisateurs spécifiques.   | 1. Le coach sélectionne une roadmap.<br>2. Définit les permissions de partage (public ou privé).<br>3. Partage la roadmap via un lien ou une invitation.                               | - Permissions mal configurées.<br>- Utilisateurs invités ne reçoivent pas l’accès.<br>- Problème serveur lors du partage.   |
| **Suivi des élèves**                | Permet aux coachs de suivre la progression des joueurs ayant accès à leurs roadmaps.                  | 1. Le coach accède à son tableau de suivi.<br>2. Visualise les statistiques de progression des joueurs.<br>3. Fournit des retours personnalisés sur des étapes spécifiques.             | - Données de progression non synchronisées.<br>- Absence d’activités récentes des joueurs.<br>- Problème de récupération.    |
| **Monétisation des roadmaps**       | Permet de définir un tarif pour l'accès à certaines roadmaps ou d’instaurer un abonnement mensuel.    | 1. Le coach configure une roadmap ou un abonnement comme payant.<br>2. Intègre un système de paiement (Stripe, PayPal).<br>3. Les utilisateurs paient pour accéder aux contenus premium. | - Paiement non validé.<br>- Problème avec la passerelle de paiement.<br>- Problème d’accès après paiement.                  |
| **Gestion des paiements**           | Permet de visualiser les paiements effectués par les utilisateurs.                                   | 1. Le coach accède à la section paiements.<br>2. Consulte l’historique des transactions.<br>3. Génère des rapports de paiements.                                                      | - Transactions manquantes dans l’historique.<br>- Problème d’exportation des rapports.<br>- Synchronisation défaillante.    |
| **Modification du profil**          | Permet aux coachs de mettre à jour leur pseudonyme, image de profil et mot de passe.                 | 1. Le coach accède à son profil.<br>2. Modifie les informations nécessaires.<br>3. Valide et enregistre les changements.                                                              | - Erreur d’enregistrement.<br>- Pseudonyme déjà pris.<br>- Problème de téléchargement de l’image de profil.                |

#### 3 - Outils communautaires

- Description : Espaces d’échange et de collaboration.
- Exigences fonctionnelles :
    - Système de commentaires et votes.
    - Création de groupes privés.
- Exigences non fonctionnelles :
    - Sécurisation des interactions via modération et filtre anti-spam.

**Tableau technique**

|Fonctionnalité|Description|Étapes|Cas d’erreur|
|---|---|---|---|
|Commenter une roadmap|Les utilisateurs peuvent laisser des commentaires sur une roadmap pour donner leur avis ou poser des questions.|1. L’utilisateur clique sur "Commenter". 2. Écrit son commentaire. 3. Valide l’envoi.|- Spam détecté. - Contenu non conforme (filtrage des propos inappropriés).|
|Noter une roadmap|Permet aux utilisateurs d’évaluer une roadmap sur une échelle de 1 à 5 étoiles.|1. L’utilisateur sélectionne une note. 2. Soumet son évaluation.|- Note déjà donnée. - Problème serveur.|

### C - Spécifications techniques

#### 1 - Exigences fonctionnelles

|**Exigence**|**Description**|
|---|---|
|**Accès multiplateforme**|La plateforme doit être accessible via desktop, mobile (iOS et Android), et tablette.|
|**Suivi de progression en temps réel**|Permettre aux utilisateurs de visualiser l’état de leurs roadmaps avec des mises à jour immédiates.|
|**Sécurisation des comptes utilisateurs**|Implémentation de la gestion des mots de passe sécurisés et de la double authentification (2FA).|
|**Multimédia intégré**|Prise en charge de vidéos, documents PDF, quiz interactifs directement intégrés dans les roadmaps.|
|**Commentaires et modération**|Les commentaires doivent être modérés en temps réel pour éviter les contenus inappropriés.|

---

#### 2 - Exigences non-fonctionnelles

|**Exigence**|**Description**|
|---|---|
|**Performance**|- Temps de chargement des pages inférieur à 2 secondes.- Support de 10 000 utilisateurs actifs simultanés.|
|**Sécurité**|- Données personnelles encryptées (AES-256).- Conformité avec la réglementation RGPD.|
|**Évolutivité**|- Architecture modulaire pour intégrer de nouvelles fonctionnalités.- Scalabilité pour gérer une base utilisateur croissante.|
|**Accessibilité**|- Conformité WCAG 2.1 pour les utilisateurs en situation de handicap.|
|**Disponibilité**|- Taux de disponibilité de 99,9 % garanti grâce à un hébergement sur un serveur cloud fiable.|
