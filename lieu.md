# Lieux


## Schema

La modélisation retenue pour les lieux suit le schéma standard. À noter : nous avons intégré des liens vers des identifiants pérennes externes via la propriété `sameAs`.

```json
{
  "@context": "https://schema.org",
  "@type": "Place",
  "@id": "https://topo.art/r#p1",
  "name": "La Vitrine",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Montréal",
    "addressRegion": "QC",
    "postalCode": "H2T 3B2",
    "streetAddress": "5445 avenue de Gaspé",
    "addressCountry": "CA"
  },
  "sameAs": [
    "http://kg.artsdata.ca/resource/K2-5987",
    "http://www.wikidata.org/entity/Q135649429"
  ]
}
```

## Documentation

https://docs.artsdata.ca/classes/place.html
