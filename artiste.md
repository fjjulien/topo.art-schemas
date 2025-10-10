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
  "identifier": {
    "@type": "PropertyValue",
    "propertyID": "isbn",
    "value":  "889647468"
  },
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
  "hasOccupation": [
    {
      "name": "Directeur",
      "description": "De l'agence Topo.art"
    }
  ],
  "disambiguatingDescription": ""
}

```
