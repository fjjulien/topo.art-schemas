# Schema Oeuvre (CreativeWork)
https://culturecreates.github.io/artsdata-data-model/classes/offer.html

```json
{
  "@type": "CreativeWork",
  "@id": "https://topo.art/r#c882",
  "additionalType": "http://iflastandards.info/ns/lrm/lrmoo/F1",
  "name": "4 heures",
  "alternateName ": "4h",
  "description": "",
  "url": "https://topo.art/4heures/",
  "image": "",
  "disambiguatingDescription ": "",
  "mainEntityOfPage": "",
  "creator": [
    {
      "@type": "Person",
      "@id": "https://topo.art/r#a8467",
      "name": "Michel Huneault",
      "url": "http://michelhuneault.com/",
      "sameAs": [
        "https://www.facebook.com/michel.huneault",
        "http://www.wikidata.org/entity/Q24705892"
      ]
    },
    {
      "@type": "Person",
      "@id": "https://topo.art/r#a8469",
      "name": "Johann Mazé",
      "sameAs": "https://johannmaze.bandcamp.com/"
    }
  ]
}
```

# Questionnement

## disambiguatingDescription
Il pourrait s’avérer intéressant de générer de façon programmatique une description de désambiguïsation suivant une formule telle que : “œuvre de {{creator.name}}...” Cela pourrait faciliter la récupération d’enregistrements de données dans une interface de recherche.

- Q?: Est-ce qu'on ajoute tous les auteurs contenu dans `creator` ?