# Orientation technique — à confirmer

## Plateforme cible

- PC Windows 10/11.
- Jeu solo et hors ligne.
- Clavier et souris.
- Sauvegardes locales.
- Distribution envisagée sous forme d'application Windows installable.

## Moteur envisagé

Godot 4 est le moteur pressenti pour la V1. Ce choix reste à confirmer après un prototype technique.

Le langage (GDScript ou C#), l'organisation des scènes, le système de données et l'architecture de sauvegarde ne sont pas encore décidés.

## Représentation visuelle

- 2D isométrique.
- Référence d'interface : écran PC 1920 × 1080.
- Sélection des bâtiments à la souris.
- États des ateliers visibles sur la vue générale.
- Ressources graphiques issues de bibliothèques adaptées ou générées, avec une direction artistique cohérente.

Aucun outil graphique spécialisé ne doit être imposé au porteur du projet pour dessiner manuellement les cartes ou les bâtiments. La production et l'intégration des ressources visuelles devront être organisées dans le flux de développement.

## Principes d'architecture à étudier

- Distinguer les règles génériques de gestion des particularités du procédé sucrier.
- Représenter les ateliers par des données : capacités, ressources, effectifs, état et niveau.
- Centraliser le calcul des flux et des goulets d'étranglement.
- Séparer simulation, interface, représentation visuelle et sauvegardes.
- Garder une architecture suffisamment extensible pour accueillir d'autres secteurs ultérieurement, sans surdimensionner la V1.

## Décisions techniques ouvertes

- Confirmation de Godot 4.
- GDScript ou C#.
- Architecture des données de production.
- Modèle de simulation temporelle.
- Format et versionnement des sauvegardes.
- Pipeline de création et d'intégration des ressources graphiques.
