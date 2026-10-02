# Eventhub

## Présentation générale

Eventhub est une plateforme de gestion d'événements et de billeterie en ligne.
Cette dernière permet aux organisateurs de créer, promouvoir et gérer leurs événements et aux utilisateurs de découvrir ainsi que réserver et participer à ces derniers.
Cette solution offre une gestion des réservations, des paiments et des participants en plus de fonctionnalytés d'analyse pour les organisateurs.

## Objectifs du projets

1. Fournir une plateforme complète de gestion d'événements et de billeterie
2. Offrir une expérience utilisateur fluide pour la recherche et la réservation
3. Permettre aux organisateurs de gérer et analyser leurs évenements
4. Sécuriser les données personnelles et les transactions
5. Créer une architecture évolutive et maintenable
6. Mettre en place une démarche DevOps complète

## Cibles utilisateurs

- **Participants** : recherchent et réservent des places
- **Organisateurs** : créent et gèrent des événements
- **Administrateurs** : gèrent la plateforme

## Image Docker Hub

L'image de production de l'API est publiée sur Docker Hub : [kelyddon/eventhub-api](https://hub.docker.com/r/kelyddon/eventhub-api).

```powershell
docker pull kelyddon/eventhub-api:latest
docker run -p 3000:3000 kelyddon/eventhub-api:latest
```

L'API sera accessible sur `http://localhost:3000` (route de test : `/health`).

## Conventions de commit

Les conventions de commit:

```
<type>[scope optionnel]: <description>

[corps optionnel]

[footer(s) optionnel(s)]
```

### Types disponibles

`feat`: nouvelle fonctionnalité

`fix`: correction de bug

`docs`: changement de documentation uniquement

`style`: formatage, sans impact sur le code (espaces, point-virgules...)

`refactor`: changement de code qui ne corrige pas un bug ni n'ajoute de fonctionnalité

`test`: ajout/correction de tests

`chore`: tâches de maintenance (config, dépendances, build...)
`perf`: amélioration de performance
