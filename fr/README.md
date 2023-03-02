# Analyse de données

Dans ce cour, nous explorerons les capacités de Python sur l'ensemble de la pile PI Data pour effectuer des analyses de données. Nous apprendrons à lire des données provenant de sources multiples telles que des bases de données, des fichiers CSV et Excel, comment les nettoyer et les transformer en appliquant des fonctions statistiques et comment les nettoyer et les transformer en appliquant des fonctions statistiques et comment créer de belles visualisations. Je te montrerai tous les outils importants de la pile PI Data : `pandas`, `matplotlib`, `seabourn` et bien d'autres.<br/>

Ce cours sera utile à la fois pour les débutants en Python qui veulent apprendre à gérer des données avec Python, et aussi pour les analyses de données traditionnelles provenant d'Excel, tableau, etc. Tu apprendras comment la programmation peut renforcer ton analyse quotidienne.

<br/>

## Définition
Je pense que l'article de Wikipedia le résume parfaitement. L'analyse de données est le processus d'inspection, de nettoyage, de transformation et de modélisation des données dans le but de découvrir des informations utiles, de tirer des conclusions et de soutenir la prise de décision. <br>

Analysons cette définition pièce par pièce. La première partie du processus d'analyse des données est généralement fastidieuse. Elle commence par la collecte des données, leur nettoyage et leur transformation en vue d'une analyse ultérieure. C'est ici que Python et les outils de données PI Excel entrent en jeu. Nous allons utiliser `pandas` pour lire, nettoyer et transformer nos données.<br/>

La modélisation des données consiste à adapter des scénarios de la vie réelle aux systèmes d'information en utilisant des statistiques inférentielles pour voir si un modèle ou un schéma se dessine. Pour cela, nous allons utiliser les fonctionnalités d'analyse statistique panéliste et les visualisations pour matplotlib et Seabourn.

> Un **panéliste** est une personne, ou un ménage, ou une entreprise membre d'un panel, et qui en tant que membre de ce panel, a pour rôle de communiquer régulièrement des données afin de rendre exploitable les études faisant l'objet du panel associé.<br/>
> Ici, il s'agit d'utiliser les fonctionnalités d'analyse statistique qui vont nous permettre d'explorer
> les données afin de mieux les exploiter.

Une fois que nous aurons traité les données et créé des modèles à partir de celles-ci, nous essaierons d'en tirer des conclusions en trouvant des anomalies qui pourraient apparaître.<br/>

Le mot *information* est ici essentiel. Si nous essayons de transformer des données en informations, nos données pourraient être par exemple une énorme **liste de tous les achats effectués à Walmart au cours de l'année dernière**, alors l'information sera quelque chose comme les **pop tarts qui se vendent mieux le mardi**.

> **Pop tarts** est le goûter préféré des américains : 2 couches de pâte sablée qui entourent un merveilleux fourrage. Ce dernier pouvant être à la framboise, à la myrtille, au beurre de cacahuètes... A manger tel quel ou à passer au grille pain.

C'est donc l'objectif final de l'analyse des données, nous devons fournir des preuves de nos conclusions, créer des rapports et des tableaux de bord lisibles afin d'aider les autres personnes ou départements avec les informations que nous avons recueillies.<br/>

De multiples acteurs utiliseront tes résultats d'analyse : marketing, ventes, cadres comptables, etc.
Ils peuvent tous avoir besoin de rapports différents ou d'un niveau de détail différent et/ou avoir besoin d'une vision différente de la même information. Bref, des outils sont disponibles aujourd'hui pour l'analyse des données.

## Outils d'analyse de données
Les outils d'analyse de données sont répartis en deux grandes catégories. A savoir:
- **Les outils d'autogestion** sont des produits proches des outils que tu peux acheter et commencer à utiliser dès la sortie de la boîte. Par exemple: *Excel*. *Tableau* et *Luchar* sont probablement les plus populaires pour l'analyse des données.
- À l'autre extrême, nous avons ce que nous appelons des **langages de programmation** que nous pouvons  appeler outils ouverts et libre d'accès. Ils ne sont pas vendus par un fournisseur individuel, mais sont constitués de bibliothèques open source. **Python**, **R** et **Julia** sont les plus populaires dans cette catégorie.<br>

### Les outils d'autogestion
Le principal avantage des outils fermés comme Tableau ou Excel est qu'ils sont généralement faciles à apprendre et à utiliser. L'entreprise propriétaire fournit une bonne documentation de son produit. Le plus gros désavantage est que la portée des fonctionnalités de ces outils est limitée. On ne peut donc pas
aller au delà.

### Les langage de programmation
En revanche, l'utilisation de Python et de l'univers des outils PI Data nous offre d'énormes avantages et une flexibilité étonnante. Si par exemple tu as besoin de récupérer des données à partir d'une API fermée en utilisant une clé secrète d'authentification, tu peux le faire. Si tu as besoin de consommer (récupérer) des données directement à partir des Kinesis de *Amazon Web Service (AWS)*, ça aussi tu peux.
Les langages de programmation les outils les plus puissants que tu peux apprendre. Un autre avantage important est la portée générale d'un langage de programmation. Il s'agit des autres
point fort d'un langage de programmation: POO, programmation système, gestion des bases de données, etc. <br/>

Le principal inconvénient d'un langage de programmation est qu'il n'est pas aussi simple à apprendre comme un outil d'autogestion. Tu dois d'abord apprendre les bases de l'algorithmie, et cela prend énormement du temps.

## Pourquoi choisir Python ?
Python est le meilleur langage de programmation. Il est simple, intuitif, et lisible, il comprend des milliers de bibliothèques pour faire pratiquement tout, de la cryptographie à l'IoT. Python est libre, gratuit et open source. Cela signifie qu'il y a des milliers d'interventions de personnes très expérimentés qui examinent les fonctions internes du langage et des bibliothèques implémentées.
De *Google* à la Banque d'Amérique, en passant par *Wall Street*, *Pentagon*, etc, ces grandes institutions font confiance à Python tous les jours. C'est à dire qu'il sera très difficile de s'en débarrasser un jour. Enfin, Python bénéficie d'un excellent esprit d'open source. La communauté est incroyable, la documentation est exhaustive.

## Quand choisir R ?
Je ne peux pas parler d'analyse de données sans parler du langage **R**. Ce dernier est également un excellent langage de programmation. R dispose d'une énorme bibliothèque de fonctions statistiques. Et si tu es dans un domaine hautement technique, qui requiert une études statistiques avancées par exemple, alors là tu es obligé d'y jeter un coup d'œil.

## Processus d'analyse de données

