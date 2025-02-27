---
id: lifecycle
title: Politique de cycle de vie des solutions
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

La société Centreon publie de nouvelles versions
de Centreon sur une cadence régulière depuis Centreon 18.10, permettant à la communauté, aux
entreprises et aux développeurs de planifier leurs feuilles de route avec la
certitude d’avoir de la visibilité en amont sur les nouvelles capacités offertes par l'open source.

<Tabs groupId="sync">
<TabItem value="À partir de la version 24.10" label="À partir de la version 24.10">

## Numéros de version

Les versions de Centreon sont nommées par l'année et la période de livraison. Par
exemple, Centreon 22.10 a été livrée en octobre 2022. Tous les modules et
composants de la collection de logiciels Centreon possèdent le même numéro de
version.

## Cadence de publication

- À partir de Centreon 24.10, Centreon publiera **une version majeure par an**.
- Des versions mineures, avec des corrections de bugs et des améliorations mineures, sortiront sur une base mensuelle.
- Une version Service Pack, cumulant toutes les modifications des versions mineures, sera généralement livrée après six mois.

## Mises à jour de maintenance et de sécurité

- Toutes les versions majeures Open Source sont supportées pendant 18 mois.
- Les versions commerciales majeures de 2024, 2026 et toutes les années paires sont des versions LTS (supportées pendant 3 ans).
- Les versions commerciales majeures de 2025, 2027 et toutes les années impaires sont supportées pendant 18 mois.

## Cycle de vie

Le cycle de vie d'une version est divisé en 3 phases :

1. Première phase : bogues de toute criticité (minor, major, critical, blocking) et correction de sécurité seront traités par priorité. Des améliorations fonctionnelles seront ajoutées.
2. Seconde phase : bogues et correction de sécurité de criticité major, critical et blocking seront traités par priorité.
3. Troisième phase : bogues et correction de sécurité de criticité blocking seront traités par priorité.

> La priorisation des bogues est faite par l'équipe produit Centreon.

La première phase du cycle de vie commence le jour de la sortie de la version.

La deuxième phase d'une version commence lorsque la prochaine version majeure est disponible. Par exemple, la publication de Centreon 25.10 lance la deuxième phase de Centreon 24.10.

La troisième phase d'une version commence lorsque la deuxième version majeure suivante est disponible. Par exemple, la sortie de Centreon 26.10 lance la troisième phase de Centreon 24.10 et la deuxième phase de Centreon 25.10.

### Schéma

Le schéma suivant présente le cycle de vie des produits Centreon à partir de la version 24.10 :

![image](../assets/releases/lifecycle-24.10.png)

## Tableau de maintenance des versions

> Tous les autres produits non décrits dans les tableaux suivants ne sont plus
> pris en charge par Centreon.

| Produit        | Sortie       | Date de fin de support    | État                |
|----------------|--------------|---------------------------|---------------------|
| Centreon 24.04 | 04/2024      | 04/2026                   | Supportée           |
| Centreon 23.10 | 10/2023      | 10/2025                   | Supportée           |
| Centreon 23.04 | 04/2023      | 04/2025                   | Supportée           |
| Centreon 22.10 | 10/2022      | 10/2024                   | Plus supportée      |
| Centreon 22.04 | 05/2022      | 05/2024                   | Plus supportée      |
| Centreon 21.10 | 11/2021      | 11/2023                   | Plus supportée      |
| Centreon 21.04 | 04/2021      | 10/2022                   | Plus supportée      |
| Centreon 20.10 | 10/2020      | 05/2022                   | Plus supportée      |
| Centreon 20.04 | 04/2020      | 10/2021                   | Plus supportée      |

</TabItem>
<TabItem value="Jusqu'à la version 24.04" label="Jusqu'à la version 24.04">

## Numéros de version

Les versions de Centreon sont nommées par l'année et la période de livraison : XX.04 pour la version de printemps,
et XX.10 pour la version d'automne. Par
exemple, Centreon 21.04 a été livrée au printemps 2021. Tous les modules et
composants de la collection de logiciels Centreon possèdent le même numéro de
version.

## Cadence de publication

Jusqu'à la version 21.04 incluse, les versions étaient supportées pendant 18 mois. Le cycle de vie d'une version est divisé en 3 phases :

1.  Première phase : bogues de toute criticité (minor, major, critical,
    blocking) et correction de sécurité seront traités par priorité
2.  Seconde phase : bogues et correction de sécurité de criticité major,
    critical et blocking seront traités par priorité.
3. Troisième phase : bogues et correction de sécurité de criticité blocking seront traités par priorité.

> La priorisation des bogues est faite par l'équipe produit
> Centreon.

La première phase du cycle de vie commence le jour de la sortie de la version.

La deuxième phase d'une version commence lorsque la prochaine version majeure
est disponible. Par exemple, la publication de Centreon 21.04 lance la deuxième
phase de Centreon 20.10.

La troisième phase d'une version commence lorsque la deuxième version majeure
suivante est disponible. Par exemple, la sortie de Centreon 21.04 lance la
troisième phase de Centreon 20.04 et la deuxième phase de Centreon 20.10.

### À partir de la version 21.10

À partir de la version 21.10, les versions sont supportées pendant 2 ans. Le cycle de vie d'une version est divisé en 2 phases de douze mois chacune.

1.  Première phase : bogues de toute criticité (minor, major, critical,
    blocking) et correction de sécurité seront traités par priorité
2.  Seconde phase : bogues et correction de sécurité de criticité major,
    critical et blocking seront traités par priorité.

> La priorisation des bogues est faite par l'équipe produit
> Centreon.

### Schéma

Le schéma suivant présente le cycle de vie des produits Centreon jusqu'à la version 24.04 :

![image](../assets/releases/lifecycle.png)

## Tableau de maintenance des versions

> Tous les autres produits non décrits dans les tableaux suivants ne sont plus
> pris en charge par Centreon.

| Produit        | Sortie       | Date de fin de support    | État                |
|----------------|--------------|---------------------------|---------------------|
| Centreon 24.04 | 04/2024      | 04/2026                   | Supportée           |
| Centreon 23.10 | 10/2023      | 10/2025                   | Supportée           |
| Centreon 23.04 | 04/2023      | 04/2025                   | Supportée           |
| Centreon 22.10 | 10/2022      | 10/2024                   | Supportée           |
| Centreon 22.04 | 05/2022      | 05/2024                   | Plus supportée      |
| Centreon 21.10 | 11/2021      | 11/2023                   | Plus supportée      |
| Centreon 21.04 | 04/2021      | 10/2022                   | Plus supportée      |
| Centreon 20.10 | 10/2020      | 05/2022                   | Plus supportée      |
| Centreon 20.04 | 04/2020      | 10/2021                   | Plus supportée      |
| Centreon 19.10 | 10/2019      | 04/2021                   | Plus supportée      |
| Centreon 19.04 | 04/2019      | 10/2020                   | Plus supportée      |
| Centreon 18.10 | 10/2018      | 04/2020                   | Plus supportée      |

</TabItem>
</Tabs>
