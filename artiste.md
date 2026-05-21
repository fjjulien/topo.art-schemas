# Le schema pour les artistes (Person)

La modélisation retenue pour les personnes suit un schéma minimal. Pour compenser la quantité minimale d'information de désambiguïsation, nous avons intégré le maximum de liens externes : l'URL du site web de l'artiste, ainsi que des liens vers ses identifiants pérennes externes via la propriété `sameAs`.

## Exemple le plus complexe supporté.

```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://topo.art/r#a8467",
  "name": "Michel Huneault",
  "alternateName": "Michel Huneault",
  "disambiguatingDescription": "Artiste québécois."
  "image": "",
  "url": "http://michelhuneault.com/",
  "sameAs": [
    "https://www.facebook.com/michel.huneault",
    "http://www.wikidata.org/entity/Q24705892"
  ]
}
```

## Documentation
[https://culturecreates.github.io/artsdata-data-model/classes/person.html](https://docs.artsdata.ca/classes/person.html)

## Notes
La propriété “identifier” est superflue. Tout d’abord, l’ISBN n’est pas un identifiant de personnes. Ensuite, tous les identifiants pertinents pour les personnes peuvent être représentés sous forme d’URI et renseignés sous la propriété “sameAs”.

La propriété “hasOccupation” devrait être utilisée pour renseigner une profession (c.-à-d. un objet de type “Occupation”) plutôt qu’un titre d’emploi. Malheureusement, l’outil Google Rich Results interprète mal les objets emplois associés à une personne. Cet enjeu est détaillé dans ce document, avec des modélisations alternatives. Si TOPO va de l’avant avec la documentation de l’occupation, nous recommandons fortement d’identifier clairement l’occupation avec un “sameAs” vers Wikidata.

## 2025-11-11
Suppression des propriétés hasOccupation et identifer.
