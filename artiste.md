# Le schema pour les artistes (Pesron)

## Documentation
https://culturecreates.github.io/artsdata-data-model/classes/person.html

## Questions :

1. Est-ce qu'on ajoute `DisambiguatingDescription` ([doc](https://kg.artsdata.ca/en/entity?uri=http%3A%2F%2Fschema.org%2FdisambiguatingDescription), [schema.org](https://schema.org/disambiguatingDescription))

## Exemple le plus complexe supporté.

```json
{
  "@type": "Person",
  "@id": "https://topo.art/r#a8467",
  "additionalType": "",
  "name": "Michel Huneault",
  "alternateName": "Michel Huneault",
  "image": "",
  "url": "http://michelhuneault.com/",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Montréal",
    "addressRegion": "QC",
    "postalCode": "H2T 3B2",
    "streetAddress": "5445 avenue de Gaspé",
    "addressCountry": "CA"
  },
  "sameAs": [
    "https://www.facebook.com/michel.huneault",
    "http://www.wikidata.org/entity/Q24705892"
  ],
  "disambiguatingDescription": ""
}
```

## Notes
La propriété “identifier” est superflue. Tout d’abord, l’ISBN n’est pas un identifiant de personnes. Ensuite, tous les identifiants pertinents pour les personnes peuvent être représentés sous forme d’URI et renseignés sous la propriété “sameAs”.

La propriété “hasOccupation” devrait être utilisée pour renseigner une profession (c.-à-d. un objet de type “Occupation”) plutôt qu’un titre d’emploi. Malheureusement, l’outil Google Rich Results interprète mal les objets emplois associés à une personne. Cet enjeu est détaillé dans ce document, avec des modélisations alternatives. Si TOPO va de l’avant avec la documentation de l’occupation, nous recommandons fortement d’identifier clairement l’occupation avec un “sameAs” vers Wikidata.

## 2025-11-11
Suppression des propriétés hasOccupation et identifer.