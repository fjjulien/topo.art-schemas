# Dépôt des schémas de données structurées de Topo.art

Ces schémas de données stucturées ont été préparés pour TOPO – Centre de création numérique, dans le cadre du projet « Guide de gestion d'archives et de documents en arts numériques » afin de servir de gabarit pour le déploiement de données structurées sur les événements en arts visuels. Les schémas ont été développés par Dessa Hayes et Frédéric Julien, de CAPACOA. Ils ont été mis à disposition dans ce dépôt par Marc-André Martin afin de documenter et de partager les fruits du projet.

Pour les fins du projet de TOPO, nous avons un défini un schéma plafond pour les types entités suivantes:

- [Artiste](artiste.md)
- [Œuvre](oeuvre.md)
- [Événement](evenement.md)
- [Lieux](lieu.md)
- [Organisation](organisation.md)

Chaque lien renvoit vers un exemple de données structurées détaillées au format JSON-LD pour le type d'entité en question. Il s'agit de schémas plafonds : chaque exemple illustre toute la gamme des propriétés disponibles pour le type d'entités selon le vocabulaire Schema.org et le modèle de données d'Artsdata. Les organismes souhaitant déployer des données stucturées sur leur site pourraient choisir d'adopter des schémas simplifiés. Pour connaître les propriétés minimales requises pour chaque type d'entité, veuillez vous référer à la [documentation d'Artsdata](https://docs.artsdata.ca/index.fr.html).

# Identifiant pérenne

En plus des schémas de métadonnées descriptives, le projet a aussi définit stratégie de production et de publication d'[identifiants pérennes](https://www.artsdata.ca/fr/ressources/bien-identifie). Ces identifiants désignent de façon univoque chaque artiste, œuvre, événement, lieu et organisme dans le site topo.art. Les identifiants pérennes sont destinés à être renseignés sous la propriété `@id` dans les données structurées schema.org, conformément aux [recommandations d'Artsdata à propos des identifants pérennes](https://docs.artsdata.ca/identifiers-guidelines/identifier-recommendations.fr.html). 

Voici le document de travail de la version 1 de l'identifiant pérenne pour les données de topo.art :

[Identifiant pérenne](identifiant-unique.md)

# Notes

## Artiste

**Question de Marc-André :**
Est-ce qu'on ajoute DisambiguatingDescription (doc, schema.org) ? 

**Réponse:**
La description de désambiguïsation est souvent générée de façon programmatique à partir d’autres métadonnées déjà renseignées. 

Par exemple, pour un artiste, on pourrait générer la description selon la formule suivante : “artiste basé à {{workLocation.addressLocality}}, {{workLocation.addressRegion}}”. 

Ce genre de description programmatique peut être générée à l’intérieur du système de TOPO.art ou sinon Artsdata peut se charger de la générer lorsque les données seront extraites, transformées et chargée. Dans le premier scénario, vous avez davantage de contrôle sur la description mais vous cela ajoute une tâche à votre cahier de charges. Dans le second scénario, il n’y a aucun effort exigé de votre part, mais vous devez accepter les descriptions telles que générées par Artsdata.

La propriété “identifier” est superflue. Tout d’abord, l’ISBN n’est pas un identifiant de personnes. Ensuite, tous les identifiants pertinents pour les personnes peuvent être représentés sous forme d’URI et renseignés sous la propriété “sameAs”.

La propriété “hasOccupation” devrait être utilisée pour renseigner une profession (c.-à-d. un objet de type “Occupation”) plutôt qu’un titre d’emploi. Malheureusement, l’outil Google Rich Results interprète mal les objets emplois associés à une personne. Cet enjeu est détaillé dans ce document, avec des modélisations alternatives. Si TOPO va de l’avant avec la documentation de l’occupation, nous recommandons fortement d’identifier clairement l’occupation avec un “sameAs” vers Wikidata.

## Oeuvre

Il pourrait s’avérer intéressant de générer de façon programmatique une description de désambiguïsation suivant une formule telle que : “œuvre de {{creator.name}}...” Cela pourrait faciliter la récupération d’enregistrements de données dans une interface de recherche.
Nous recommandons d’ajouter : "additionalType": "http://iflastandards.info/ns/lrm/lrmoo/F1",
Justification : La définition de schema : CreativeWork est plus générique que celle de lrmo:F1 Work. Avec cette précision, il serait plus facile de distinguer les œuvres d’art des CreativeWorks un peu moins artistiques telles que des pages Web.
Q11424 (film) est un type spécifique d’œuvre qui ne conviendrait pas pour décrire toute la gamme des œuvres présentées sur topo.art. 
Si vous souhaitez assigner des types spécifiques, il faudrait définir une collection de concepts Wikidata et de bien les définir pour que tous les utilisateurs qui font de la saisie de données soient en mesure de faire la même détermination quant à la forme de l’œuvre.
Si vous souhaitez définir un « type par défaut », alors il faudrait choisir un concept plus générique de sorte que l’affirmation soit toujours vraie peu importe le type d’œuvre. Q838948 (œuvre d’art) pourrait constituer un assez bon choix de valeur par défaut.
Prenez note que la hiérarchie des formes d’art dans Wikidata n’est pas tout à fait d’une clarté limpide…
“Image”: Considérez décrire l’image comme un “ImageObject”. Cela vous permettra de renseigner le crédit photo.

## Organisation

Sous additionalType, on pourrait mettre une valeur de la vocabulaire contrôlée pour les types d’organismes d’Artsdata (http://kg.artsdata.ca/resource/ArtsOrganization peut constituer une bonne valeur par défaut)
