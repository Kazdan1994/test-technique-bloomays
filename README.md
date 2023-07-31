<img alt="📝" aria-label="📝" src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f4dd.svg" style="position: absolute; top: 0; left: 0; opacity: 1; width: 78px; height: 78px;">
<br/>

use Case technique
==================

Loïc Calvy

28 mars

v1.0.0

<br/>

#### Test technique Bloomays:

<span style="color:rgba(223, 84, 82, 1);fill:rgba(223, 84, 82, 1)">Temps mis à disposition: max 1 semaine</span>

👉 Utilisation de Reactjs obligatoire

👉 Utilisation d’Expressjs ou NestJS obligatoire

<br/>

#### Front :

👉 Reproduire le composant LeavingArrivingBloomers. en image ci-dessous.

Ce composant, regroupe deux types de freelances (bloomers). Les bloomers entrant et bloomers sortant. Dans le premier, nous y voyons les bloomers entrant à partir d’aujourd’hui jusqu'à la fin du mois prochain. Donc si nous sommes le 17 juin, tu verras les bloomers entrant du 17 juin au 31 juillet.

Même chose pour les bloomers sortant.

Pour ça nous nous appuyons sur les clées “beginDate” et “endDate” de l’objet mission

![👉](https://bloomays.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F706b50b6-4f66-4f25-af8d-0ec800d66356%2Farriving.png?table=block&id=3b25a385-b980-4bf6-bacb-e88eabd86e31&spaceId=81894261-1dd5-42e9-85e5-b486231ba5b4&width=580&userId=&cache=v2)

#### Back:

👉 Créer un server Express contenant une route renvoyant un tableau d’objet (Missions)

Voici la structure des données brut qui doivent être renvoyer par ta route:

```js
const missions = [
  {
    id: '',
    label: '',
    beginDate: '',
    endDate: '',
    missionType: '',
    freelance: {
      id: '',
      firstname: '',
      lastname: '',
      email: '',
    },
  },
// ...
];
```

#### Algo:

👉 Une fois les données reçues du back, il va falloir les manipuler pour avoir une structure permettant un affichage par date d’arrivée (pour les bloomers entrant) et par date de sortie (pour les bloomers sortant)

```js
const arriving = {
  '2020-09-18': [
    {
      firstname: 'Michel',
      lastname: 'Cacahuete',
      beginMission: '2020-09-18',
      endMission: '2021-09-18',
      id: 42,
    },
    {
      firstname: 'Sandy',
      lastname: 'Courgette',
      beginMission: '2020-09-18',
      endMission: '2021-09-18',
      id: 9,
    },
  ],
  '2020-10-18': [
    {
      firstname: 'Laura',
      lastname: 'Choux',
      beginMission: '2020-10-18',
      endMission: '2021-10-18',
      id: 16,
    },
  ]
};

const leaving = {
  '2021-07-18': [
    {
      firstname: 'Michel',
      lastname: 'Cacahuete',
      beginMission: '2020-02-18',
      endMission: '2021-07-18',
      id: 42,
    },
    {
      firstname: 'Sandy',
      lastname: 'Courgette',
      beginMission: '2020-09-03',
      endMission: '2021-07-18',
      id: 9,
    },
  ],
  '2021-10-18': [
    {
      firstname: 'Laura',
      lastname: 'Choux',
      beginMission: '2020-10-18',
      endMission: '2021-10-18',
      id: 16,
    },
  ]
};
```

Pour organiser les données reçue du back, créer une fonction classant les missions par date, de la courante à la plus lointaine dans le future.

#### Bonus:

**👉** Plutôt que de renvoyer du back de la data hardcodé, pourquoi ne pas tenter d’établir une connection avec [Airtable](https://airtable.com/api), d’y créer des tables, et de la requêter avec ton back ? :)

Bon chance!
