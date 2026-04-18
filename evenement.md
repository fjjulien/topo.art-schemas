# Événements

## Schéma

### Exposition

Cet exemple de données structurées décrit à la fois l’exposition, avec son horaire et son lieu, ainsi que l’œuvre qui est exposée. Le lien entre l’exposition et l’œuvre est articulé avec la propriété `workFeatured`.

```
<script type="application/ld+json">
{
  "@context": "http://schema.org",
  "@type": "Event",
  "@id": "https://topo.art/r#e1",
  "additionalType": "http://kg.artsdata.ca/resource/ExhibitionEvent",
  "Name": "4 heures | Michel Huneault et Johann Mazé",
  "alternateName": "Film d’observation non linéaire",
  "eventSchedule": {
    "@type": "Schedule",
    "startDate": "2023-05-26",
    "endDate": "2023-07-30",
    "repeatFrequency": "P1W",
    "byDay": [
      "http://schema.org/Monday",
      "http://schema.org/Tuesday",
      "http://schema.org/Wednesday",
      "http://schema.org/Thursday",
      "http://schema.org/Friday",
      "http://schema.org/Saturday"
    ],
    "startTime": "10:00:00",
    "endTime": "17:00:00",
    "scheduleTimezone": "America/Montreal"
  },
  "location": [
    {
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
    },
    {
      "@type": "VirtualLocation",
      "url": "https://topo.art/4heures//"
    }
  ],
  "eventStatus": "https://schema.org/EventScheduled",
  "eventAttendanceMode": "https://schema.org/MixedEventAttendanceMode",
  "description": "Invité par TOPO et un partenaire du Pays Basque, Bitamine Faktoria, en juin 2022, Michel Huneault a effectué une résidence de création lors de laquelle il a développé avec son collègue Johann Mazé une nouvelle œuvre autour de la vie à la frontière entre la France et l’Espagne. Les deux versions de l’œuvre, en vitrine et en ligne, présentent une succession d’un peu plus de 200 plans séquences de 1 à 2 minutes chacun, associant un court extrait vidéo à une bande sonore asynchrone. L’expérience non linéaire, lente et contemplative, offre une réflexion nuancée sur les réalités transfrontalières.",
  "url": "https://topo.art/programmation/4-heures-michel-huneault-et-johann-maze/",
  "image": "https://topo.art/chantier/wp-content/uploads/2023/10/rivierekayak.png",
  "keywords": "Frontière, Pays Basque, arts numérique",
  "organizer": [
    {
      "@type": "Organization",
      "@id": "https://topo.art/r#o1",
      "name": "TOPO",
      "url": "https://topo.art/",
      "sameAs": [
        "https://www.facebook.com/topomtl/",
        "http://kg.artsdata.ca/resource/K2-5986",
        "http://www.wikidata.org/entity/Q107051816"
      ]
    }
  ],
  "workFeatured": [
    {
      "@type": "CreativeWork",
      "@id": "https://topo.art/r#c882",
      "additionalType": "http://www.wikidata.org/entity/Q11424",
      "name": "4 heures",
      "url": "https://topo.art/4heures/",
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
  ],
  "isAccessibleForFree": "true"
}
</script>
```

### Vernissage

Dans cet exemple, étant donné qu’un vernissage est un événement social célébrant une nouvelle exposition (plutôt que l’exposition elle-même), le type `SocialEvent` est plus approprié que le type `ExhibitionEvent`. Le lien entre le vernissage et l’exposition auquel il se réfère est articulé avec la propriété `about`, qui pointe vers l’identifiant pérenne de l’exposition.

```
<script type="application/ld+json">
{
   "@context": "http://schema.org",
   "@type": "Event",
   "@id": "https://topo.art/programmation/4-heures-michel-huneault-et-johann-maze/#vernissage",
   "additionalType": "http://kg.artsdata.ca/resource/SocialEvent",
   "name": "Vernissage 4 heures | Michel Huneault et Johann Mazé",
   "about": "https://topo.art/r#e1",
   "startDate": "2023-05-25T17:00:00-04:00",
   "endDate": "2023-05-25T19:00:00-04:00",
   "location":
         {
            "@type": "Place",
            "name": "La Vitrine",
            "address": {
               "@type": "PostalAddress",
               "addressLocality": "Montréal",
               "addressRegion": "QC",
               "postalCode": "H2T 3B2",
               "streetAddress": "5445 avenue de Gaspé",
               "addressCountry": "CA"
                                    },
            "sameAs":[
               "http://kg.artsdata.ca/resource/K2-5987",
               "http://www.wikidata.org/entity/Q135649429"
                               ]
              },
   "eventStatus": "https://schema.org/EventScheduled",
   "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
   "url": "https://topo.art/programmation/4-heures-michel-huneault-et-johann-maze/",
   "image": "https://topo.art/chantier/wp-content/uploads/2023/10/rivierekayak.png",
   "organizer": [{
      "@type": "Organization",
      "name": "TOPO",
      "url": "https://topo.art/",
      "sameAs": [
         "https://www.facebook.com/topomtl/",
         "http://kg.artsdata.ca/resource/K2-5986",
         "http://www.wikidata.org/entity/Q107051816"]
                      }],
   "isAccessibleForFree": "true"
}
</script>
```

## Documentation

https://docs.artsdata.ca/classes/event.fr.html

## DefinedTerms

### Type de présence aux événements

```json
{
  "attendanceMode": [
    "https://schema.org/MixedEventAttendanceMode",
    "https://schema.org/OfflineEventAttendanceMode",
    "https://schema.org/OnlineEventAttendanceMode"
  ]
}
```

### Status d'événement

https://schema.org/EventStatusType

```
EventCancelled
EventMovedOnline
EventPostponed
EventRescheduled
EventScheduled
```

### eventSchedule

repeatFrequency
https://schema.org/duration 
https://en.wikipedia.org/wiki/ISO_8601#Durations

https://en.wikipedia.org/wiki/ISO_8601

### Les types d'événements

https://docs.artsdata.ca/event-types.fr.html

Le [vocabulaire contrôlé d'Artsdata pour les types d'événements](https://docs.artsdata.ca/event-types.fr.html) a été élaboré spécifiquement pour le secteur des arts. On y retrouve des concepts qui ne sont pas présents dans schema.org.

| CURI | Libellé préféré | Description |
| - | - | - |
| [Event](http://kg.artsdata.ca/resource/Event) | Événement | Une activité organisée qui a lieu à une heure et un lieu précis. |
| [EventSeries](http://kg.artsdata.ca/resource/EventSeries) | Série d'événements | Une série cohérente d'événements individuels, de spectacles, de rassemblements et/ou de performances avec une continuité organisationnelle. |
| [Class](http://kg.artsdata.ca/resource/Class) | Cours | Une série d'événements offrant une expérience d'apprentissage structurée à un moment et un lieu spécifiques. |
| [TalkEvent](http://kg.artsdata.ca/resource/TalkEvent) | Discussion | Un événement au cours duquel une ou plusieurs personnes parlent devant un public. |
| [PerformingArtsEvent](http://kg.artsdata.ca/resource/PerformingArtsEvent) | Représentation | Un événement au cours duquel une œuvre scénique est exécutée en publique. |
| [RehearsalEvent](http://kg.artsdata.ca/resource/RehearsalEvent) | Répétition devant public | Un événement où le processus de création d’une œuvre de spectacle et sa préparation en vue de sa présentation sont partagés avec le public. |
| [CircusPerformance](http://kg.artsdata.ca/resource/CircusPerformance) | Représentation de cirque | Une représentation qui implique une série de prestations affichant des compétences humaines, du courage, de l'humour et/ou des astuces avec des animaux. |
| [ComedyPerformance](http://kg.artsdata.ca/resource/ComedyPerformance) | Représentation d’humour | Une représentation mettant en vedette un ou plusieurs comédiens racontant et/ou jouant des blagues destinées à faire rire un public. |
| [DancePerformance](http://kg.artsdata.ca/resource/DancePerformance) | Représentation de danse | Une représentation présentant l’exécution d’une œuvre chorégraphique. |
| [MusicalTheatrePerformance](http://kg.artsdata.ca/resource/MusicalTheatrePerformance) | Représentation de théâtre musical | Une représentation présentant la représentation d'une œuvre musico-dramatique du genre du théâtre musical, combinant musique, chant et jeu d'acteur pour raconter une histoire. |
| [OperaPerformance](http://kg.artsdata.ca/resource/OperaPerformance) | Représentation d'opéra | Une représentation présentant la représentation d'une œuvre musico-dramatique du genre opéra, mêlant chant, mise en scène et narration scenique. |
| [MusicPerformance](http://kg.artsdata.ca/resource/MusicPerformance) | Concert | Un représentation mettant en vedette l'exécution d'une œuvre musicale impliquant un ou plusieurs artistes chantant et/ou jouant des instruments. |
| [SpokenWordPerformance](http://kg.artsdata.ca/resource/SpokenWordPerformance) | Représentation de création parlée | Une représentation mettant en vedette de la poésie interprétée devant un public. |
| [TheatrePerformance](http://kg.artsdata.ca/resource/TheatrePerformance) | Représentation de théâtre | Une représentation dans lequel des acteurs jouent une pièce écrite pour la scène.  |
| [StorytellingPerformance](http://kg.artsdata.ca/resource/StorytellingPerformance) | Représentation de conte | Une représentation qui utilise des mots et des actions pour transmettre au public les éléments et le contenu d'une narration spécifique. |
| [VarietyPerformance](http://kg.artsdata.ca/resource/VarietyPerformance) | Représentation de variétés | Un événement des arts de la scène mettant en vedette plusieurs performances d'art ou de genres différents. |
| [PerformanceArt](http://kg.artsdata.ca/resource/PerformanceArt) | Performance artistique | Une représentation qui produise une œuvre éphémère au cours de son exécution. |
| [Festival](http://kg.artsdata.ca/resource/Festival) | Festival | Un événement avec un ensemble organisé d’activités axées sur un thème qui dure de quelques heures à plusieurs semaines. |
| [ChildrensEvent](http://kg.artsdata.ca/resource/ChildrensEvent) | Événement pour enfants | Un événement mettant en vedette le contenu éducatif et/ou artistique approprié a tous âges. |
| [ExhibitionEvent](http://kg.artsdata.ca/resource/ExhibitionEvent) | Exposition | Un événement où une collection d'objets sélectionnés est regroupée selon un thème dans le but d'être présentée au public. |
| [ResidencyEvent](http://kg.artsdata.ca/resource/ResidencyEvent) | Résidence | Un événement dans laquelle une organisation artistique parraine un ou plusieurs artistes et soutient leur travail en leur donnant accès aux ressources dont dispose l'organisation. |
| [ScreeningEvent](http://kg.artsdata.ca/resource/ScreeningEvent) | Projection | Un événement qui présente du contenu audiovisuel à un public. |
| [SocialEvent](http://kg.artsdata.ca/resource/SocialEvent) | Événement social | Un événement organisé pour qu'un groupe de personnes se rencontre et/ou interagisse les unes avec les autres. |
| [WorkshopEvent](http://kg.artsdata.ca/resource/WorkshopEvent) | Atelier | Un événement où les gens apprennent et/ou pratiquent un sujet ou une activité spécifique. |
| [MasterclassEvent](http://kg.artsdata.ca/resource/MasterclassEvent) | Cours de maître | Un événement d'atelier mettant en vedette un expert dans un domaine spécifique qui enseigne et/ou conseille d'autres artistes dans le même domaine, et offre aux nouveaux artistes l'avantage de l'expérience de l'expert. |
| [PostshowTalk](http://kg.artsdata.ca/resource/PostshowTalk) | Discussion après-spectacle | Un événement mettant en vedette des artistes discutant avec le public après une performance. |
| [PreshowTalk](http://kg.artsdata.ca/resource/PreshowTalk) | Discussion avant-spectacle | Un événement mettant en vedette des artistes discutant avec le public avant une performance. |
| [PowWow](http://kg.artsdata.ca/resource/PowWow) | Pow-wow | Un festival célébré par les communautés autochtones d'Amérique du Nord, respectant des protocoles cérémoniels précis et incluant des danses, des chants et du tambour. |
| [Competition](http://kg.artsdata.ca/resource/Competition) | Concours | Un événement dans lequel les gens s'affrontent pour remporter des prix. |
| [Convention](http://kg.artsdata.ca/resource/Convention) | Congrès | Une série d'événements comprenant des activités de prise de parole en direct, y compris des conférences, des ateliers et/ou des événements sociaux. |
| [SocialDance](http://kg.artsdata.ca/resource/SocialDance) | Danse sociale | Un événement social où des personnes se réunissent pour danser ensemble dans un cadre structuré ou informel. |
| [AwardsEvent](http://kg.artsdata.ca/resource/AwardsEvent) | Événement de remise de prix | Un événement social où des personnes, groupes, organismes ou oeuvres se voient décerner des distinctions. |
| [LiveFilmConcert](http://kg.artsdata.ca/resource/LiveFilmConcert) | Ciné-concert | Un événement de projection où des musiciens en direct interprètent la bande-son d’un film en temps réel. |
