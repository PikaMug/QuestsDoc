# Planificateur

Une fois que vous vous serez familiarisé avec l'[éditeur de quête](../setup/quests-editor.md) vous vous poserez peut-être des questions sur la sélection "Modifier le planificateur". Ce sous-menu contient des contrôles pour quand votre quête devrait être disponible, basée sur le temps réel :

![](https://camo.githubusercontent.com/07cea0e4af2b6bde23df1ada96f63d46b090cfe97a32b8889eb3599245245ff8/68747470733a2f2f692e696d6775722e636f6d2f7743374134396a2e706e67)

<details>

<summary>Développez pour voir la ventilation.</summary>

1. Time the quest should become available
2. Time the quest should cease to be available
3. Length until quest is available again
4. Length to wait after completing quest
5. If true, players can take quest immediately after repeat cycle ends
6. Finish working on your quest planner

</details>

Pour mieux comprendre ces sélections, des exemples sont fournis ci-dessous.

**Quête journalière**

Dans le monde réel, la plupart des entreprises ne sont ouvertes que pendant les heures de pointe. De même, vous souhaiterez peut-être que votre quête ne soit disponible qu'à certains moments de la journée. Voici comment une telle quête peut apparaître dans quests.yml :

```
custom1:
    name: Quotidien
    ...
    planner:
      start: 11:1:2020:9:0:0:SystemV/EST5
      end: 11:1:2020:17:0:0:SystemV/EST5
      repeat: 86400
      cooldown: 32400
      override: true
```

La **date de départ (start)** est fixé au 11 janvier 2020 à 9h00. La **date de fin (end)** est fixée au 11 janvier 2020 à 17h00. Cela signifie que la quête ne sera disponible que pendant huit heures.

Comme nous voulons que les joueurs puissent effectuer la quête tous les jours, le **cycle de répétition (repeat)** est défini sur 86 400 secondes (24 heures). Ce temps d'attente est basé sur la date de début, donc la quête sera ensuite disponible le 12 janvier 2020, puis à nouveau le 13, et ainsi de suite. Tout comme la durée d'origine, il ne sera toujours disponible qu'entre 9h00 et 17h00 tous les jours.

Enfin, nous avons défini un **temps de recharge du joueur (cooldown)** de 32 400 secondes (9 heures) car nous ne voulons pas que le joueur reprenne notre quête s'il la termine avant 17h00. Cela garantit que même les joueurs les plus rapides ne pourront pas reprendre la quête avant le lendemain. Si vous souhaitez que les joueurs puissent effectuer la quête à 9h00 le lendemain, que leur temps de recharge ait expiré ou non, vous pouvez définir la priorité **ignorer le temps de recharge après répétition (override)** sur _true_.

**New Years' Celebration**

Créons une quête pour une fête du Nouvel An. Veuillez observer l'exemple suivant tel qu'il apparaîtrait dans quests.yml:

```
custom1:
    name: Préparationdelanouvelleannée
    ...
    planner:
      start: 31:12:2020:23:0:0:SystemV/EST5
      end: 1:1:2021:0:0:0:SystemV/EST5
      repeat: 31536000
      cooldown: 3600
      override: false
```

La **date de début** est fixée au 31 décembre 2020 à 23h00. La **date de fin** est fixée au 1er janvier 2021 à minuit. Cela signifie que la quête ne sera disponible que pendant une heure.

Puisque nous voulons célébrer _chaque année_, le **cycle de répétition** est défini sur 31536000 secondes (une année civile). Ce temps d'attente est basé sur la date de début, donc la quête sera ensuite disponible le 31 décembre 2021, puis à nouveau le 31/12/2022, et ainsi de suite. Il ne sera disponible que pendant une heure, tout comme la durée d'origine.

Enfin, nous avons défini un **temps de recharge du joueur** de 3 600 secondes (une heure) car nous ne voulons pas que le joueur reprenne notre quête s'il la termine en moins d'une heure. Cela garantit que même les joueurs les plus rapides ne pourront pas reprendre la quête avant l'année prochaine.
