<img alt="📝" aria-label="📝" src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f4dd.svg" style="position: absolute; top: 0; left: 0; opacity: 1; width: 78px; height: 78px;">
<br>
<br>
<br>
<br>

use Case technique
==================

<div style="display: flex; align-items: flex-start; position: relative; font-size: 14px;"><div style="flex-grow: 1; min-width: 0;"><div style="align-items: center; position: relative; display: flex; flex-direction: row; padding: 6px 16px 0 18px; user-select: none;"><div style="margin-right: 10px; margin-top: 2px; user-select: none;"><div style="background: rgb(25, 25, 25); border-radius: 100%; box-shadow: rgba(15, 15, 15, 0.2) 0 2px 4px;"><div style="border-radius: 100%; width: 20px; height: 20px; max-width: 100%; max-height: 100%; display: flex; align-items: center; justify-content: center; user-select: none; opacity: 1;"><div style="width: 100%; height: 100%;"><img alt="" src="https://bloomays.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fpublic.notion-static.com%2Fee98369a-50d4-4619-9269-6ff3a753aa4f%2Floic_calvy_2019_-_square.jpg?width=40&amp;userId=&amp;cache=v2" referrerpolicy="same-origin" style="display: block; object-fit: cover; border-radius: 100%; width: 100%; height: 100%;"></div></div></div></div><div style="overflow: hidden;"><span style="font-weight: 600; white-space: normal;">Loïc Calvy</span><div style="font-size: 12px; line-height: 16px; color: rgba(255, 255, 255, 0.282); margin: 0 6px; flex-basis: 140px; white-space: normal; flex-grow: 1; display: inline;"><div style="display: inline;">28 mars</div></div></div></div><div style="padding-left: 47px; padding-right: 16px;"><div style="cursor: text;"></div></div><div style="padding: 0 16px 3px;"><div style="position: relative;"><div style="display: -webkit-box; -webkit-box-orient: vertical;"><div><div spellcheck="true" data-content-editable-leaf="true" contenteditable="false" style="max-width: 100%; width: 100%; white-space: pre-wrap; word-break: break-word; caret-color: rgba(255, 255, 255, 0.81); cursor: text; padding-left: 32px;">v1.0.0</div></div></div></div></div><div style="margin: 0 14px 0 50px;"></div><div></div></div></div>
<hr>

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
