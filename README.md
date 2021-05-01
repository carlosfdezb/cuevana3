<p align="center">
  <img src="./assets/img/logo.png" alt="Cuevana3 Scraper"/>
</p>

  
<p align="center">
 Cuevana3 scraper is a content provider of the latest in the world of movies and tv show in Latin Spanish dub or subtitled.
</p>

![npm](https://img.shields.io/npm/v/npm?style=flat-square) ![GitHub package.json version](https://img.shields.io/github/package-json/v/carlosfdezb/cuevana3?style=flat-square) ![NPM](https://img.shields.io/npm/l/cuevana3?style=flat-square)

[![NPM](https://nodei.co/npm/cuevana3.png)](https://nodei.co/npm/cuevana3/)

## 📌 Installation
```
npm install cuevana3
```

## 📖 Documentation
Available methods:

- [getMovies](#-getMoviestype): Returns a list with the movies according to the indicated type.
- [getSeries](#-getSeriestype): Returns a list with the series according to the indicated type.
- [getDetail](#-getDetailid): Returns the detail of the selected movie/series.
- [getByGenre](#-getByGenreid-page): Returns a list with movies according to the indicated genre and page.
- [getByActor](#-getByActorid-page): Returns a list with movies according to the indicated actor.
- [getSearch](#-getSearchquery-page): Returns a list with movies/series according to query.
- [getLinks](#-getLinksid): Returns a list of links of selected movie or episode of serie.
- [getDownload](#-getDownloadid): Returns a list of download links of selected movie or episode of serie.
- [getTrailer](#-getTrailerid): Returns a trailer link of selected movie/serie.


## 🚩 getMovies(type)
Returns a list with the movies according to the indicated `type`.

| VALUE | TYPE |
| -----|----- |
| Latest movies added | 0 |
| Premiere movies | 1 |
| Most viewed movies | 2 |
| Top rated movies | 3 |
| Latin dub movies | 4 |
| Spanish dub movies | 5 |
| Subtitled movies | 6 |

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getMovies(0)
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    id: '42040/without-remorse',
    title: 'Sin remordimientos',
    poster: 'https://cuevana3.io/wp-content/uploads/2021/04/sin-remordimientos-42040-poster-204x300.jpg',
    year: '2021',
    sypnosis: 'Un ex Navy SEAL convertido en agente de la CIA busca venganza después de que su novia es asesinada por un narcotraficante de Baltimore.',
    rating: '4.42',
    duration: '1h 49m',
    director: [ 'Stefano Sollima' ],
    genres: [ 'Acción', 'Aventura', 'Thriller' ],
    cast: [ 'Adrian Rawlins', 'Alec Rosenthal', 'Artjom Gilz' ]
  },
  {
    id: '5820/journeyman-ihy0v',
    title: 'Journeyman',
    poster: 'https://cuevana3.io/wp-content/uploads/2018/08/journeyman-5820-poster-200x300.jpg',
    year: '2018',
    sypnosis: 'Sigue a un campeón del mundo de boxeo en el declive de su carrera que acepta participar en un último combate para poder retirarse […]',
    rating: '4.25',
    duration: '1h 32m',
    director: [ 'Paddy Considine' ],
    genres: [ 'Drama' ],
    cast: [ 'Anthony Welsh', 'Jodie Whittaker', 'Paddy Considine' ]
  },
  ...
]
```

## 🚩 getSeries(type)
Returns a list with the series according to the indicated `type`.

| VALUE | TYPE |
| -----|----- |
| Latest series added | 0 |
| Premiere series | 1 |
| Top rated series | 2 |
| Most viewed series | 3 |
| Latest episodes added | 4 |

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getMovies(4)
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    id: 'episodio/the-innocent-1x8',
    episode: 'The Innocent 1x8',
    poster: 'https://image.tmdb.org/t/p/w185/o2Xf958jMUS7H7ggZLt7qYyGTD.jpg' 
  },
  {
    id: 'episodio/the-innocent-1x7',
    episode: 'The Innocent 1x7',
    poster: 'https://image.tmdb.org/t/p/w185/4LCdnygQ5bXyWrb4aZfz2nL4A5j.jpg'
  },
  ...
]
```
  
## 🚩 getDetail(id)
Returns the detail of the selected movie/series using `id`.

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getDetail('21711/joker')
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    id: '21711/joker',
    poster: 'https://image.tmdb.org/t/p/w600_and_h900_bestv2/v0eQLbzT6sWelfApuYsEkYpzufl.jpg',
    background: 'https://image.tmdb.org/t/p/w1280/ftkY1xIQ6ianSVp3EDufPVPLwa2.jpg',
    title: 'Joker',
    original_title: 'Joker',
    sypnosis: 'Situada en los años 80′. Un cómico fallido es arrastrado a la locura, convirtiendo su vida en una vorágine de caos y delincuencia que poco a poco lo llevará a 
ser el psicópata criminal más famoso de Gotham.',
    year: '2019',
    duration: '2h 1m',
    rating: '4,01',
    director: [ 'Todd Phillips' ],
    genres: [
      { id: 'crimen', genre: 'Crimen' },
      ...
    ],
    cast: [
      { id: 'joaquin-phoenix', name: 'Joaquin Phoenix' },
      { id: 'robert-de-niro', name: 'Robert De Niro' },
      ...
    ],
    links: {
      latino: [
        {
          url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4N1ZUN3ErYUhaV1IxYjBjcDI5MjRlWGo5OG1lb1JpZ0FWWFU1RFNyUEkvcDRDTDZOWGJhMUEzWTBRaUt6VmhuSTMrbUYvVG05b01rZFNkNEZiaGFnL3NtZlEyMDB5QUl0WnM2TXpibmJ4dWh3PT0'
        },
        ...
      ],
      espanol: [
        {
          url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4NVlpdllSTVEvMXRSam00M3N1TkJMSXJhaHpvVGVuZjVtdzVUN0NDTWJsQW9YTldwamIzN3dIbFlzTzFyMUY5UUlKdFNiaklWR2dCeWpaeFpNSTlId0hVWCtVeW93a0N2VCs5Nk9uZXRoMndRPT0'
        },
        ...
      ],
      sub: [
        {
          url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4NVZvR3BFTXY5NFI3TXpwUHVldVJyVHFQSmpMOVdYeGxGbFFDditCSDdZNnYrak4yL0lDTFJkU3oxZ1NaR2ZNU3NxRS81SnBMWUV4ZHBtSVA4b0s1MldIbXBXcTNPRENiMlJoZGdJNG5uNmNBPT0'
        },
        ...
      ]
    }
  }
]
```

## 🚩 getByGenre(type, page)
Returns a list with movies according to the indicated `genre` and `page`.

| VALUE | TYPE |
| -----|----- |
| Acción | 0 |
| Animación | 1 |
| Aventura | 2 |
| Bélico guerra | 3 |
| Biografía | 4 |
| Ciencia ficción | 5 |
| Comedia | 6 |
| Crimen | 7 |
| Documentales | 8 |
| Drama | 9 |
| Familiar | 10 |
| Fantasía | 11 |
| Misterio | 12 |
| Musical | 13 |
| Romance | 14 |
| Terror | 15 |
| Thriller | 16 |

| Pages |
| -----|
| [1 .. total page unknown] |

Example:
```js
const cuevana3 = require('cuevana3');

//6 : Comedia
cuevana3.getByGenre(6,1)
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    id: '12299/book-of-monsters',
    title: 'Book of Monsters',
    poster: 'https://cuevana3.io/wp-content/uploads/2019/04/book-of-monsters-12299-poster-200x300.jpg',
    year: '2018',
    sypnosis: 'La fiesta de cumpleaños de Sophie se convierte en un baño de sangre cuando seis monstruos terroríficos descienden a su casa, con la intención […]',
    rating: '2.78',
    duration: '1h 24m',
    director: [
      'James Martin Buck',
      'Oliver Mitchell',
      'Paul Morris',
      'Stewart Sparke'
    ],
    genres: [ 'Acción', 'Comedia', 'Terror' ],
    cast: [ 'Anna Dawson', 'Arron Dennis', 'Ben Hartley' ]
  },
  {
    id: '42090/the-mitchells-vs-the-machines',
    title: 'Los Mitchell contra las máquinas',
    poster: 'https://cuevana3.io/wp-content/uploads/2021/05/los-mitchell-contra-las-maquinas-42090-poster-200x300.jpg',
    year: '2021',
    sypnosis: 'Katie Mitchell, una adolescente creativa y poco convencional, es aceptada en la escuela de cine de sus sueños, pero sus planes para volar a […]',
    rating: '3.86',
    duration: '1h 54m',
    director: [ 'Jeff Rowe', 'Michael Rianda', 'Peter Szilagyi' ],
    genres: [ 'Animación', 'Aventura', 'Comedia' ],
    cast: [ 'Abbi Jacobson', 'Alex Hirsch', 'Alison Rich' ]
  },
  ...
]
```

## 🚩 getByActor(id, page)
Returns a list with movies according to the indicated actor using `id`.

| Pages |
| -----|
| [1 .. total page unknown] |

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getByActor('joaquin-phoenix',1)
  .then((res) => console.log(res));
```

Results:
```json
  [
    {
      id: '21711/joker',
      title: 'Joker',
      poster: 'https://cuevana3.io/wp-content/uploads/2019/10/joker-21711-poster-209x300.jpg',
      year: '2019',
      sypnosis: 'Situada en los años 80′. Un cómico fallido es arrastrado a la locura, convirtiendo su vida en una vorágine de caos y delincuencia que […]',
      rating: '4.01',
      duration: '2h 1m',
      director: [ 'Todd Phillips' ],
      genres: [ 'Crimen', 'Drama', 'Thriller' ],
      cast: [ 'Adrienne Lovette', 'Bill Camp', 'Brett Cullen' ]
    },
    {
      id: '20523/les-freres-sisters',
      title: 'Los hermanos Sisters',
      poster: 'https://cuevana3.io/wp-content/uploads/2019/09/los-hermanos-sisters-20523-poster-200x300.jpg',
      year: '2018',
      sypnosis: '1850. Los hermanos Charlie y Eli Sisters viven en un mundo salvaje y hostil, en plena fiebre del oro. Tienen las manos manchadas de […]',
      rating: '3.94',
      duration: '2h 1m',
      director: [
        'Emmanuel Granados',
        'Jacques Audiard',
        'Jean-Baptiste Pouilloux'
      ],
      genres: [ 'Comedia', 'Crimen', 'Drama' ],
      cast: [ 'Aidan O'Hare', 'Aldo Maland', 'Allison Tolman' ]
    },
    ...
  ]
```

## 🚩 getSearch(query, page)
Returns a list with movies/series according to `query`.

| Pages |
| -----|
| [1 .. total page unknown] |

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getSearch('toy story',1)
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    id: '16941/toy-story-4',
    title: 'Toy Story 4',
    poster: 'https://cuevana3.io/wp-content/uploads/2019/06/61hlB1D6t1Ctbjk1YtW8V0Ij21Y-200x300.jpg',
    year: '2019',
    sypnosis: 'Las aventuras de este dúo tan carismático les obligarán de nuevo salir al extraño y gigantesco mundo exterior, en una nueva misión imposible. Con […]',
    rating: '3.91',
    duration: '1h 30m',
    director: [ 'Josh Cooley' ],
    genres: [ 'Animación', 'Aventura', 'Comedia' ],
    cast: [ 'Alan Oppenheimer', 'Ally Maki', 'Annie Potts' ]
  },
  {
    id: '11526/toy-story-3',
    title: 'Toy Story 3',
    poster: 'https://cuevana3.io/wp-content/uploads/2019/03/toy-story-3-11526-poster-200x300.jpg',
    year: '2010',
    sypnosis: 'Sabiendo que su dueño Andy, que ya no es un niño, se prepara para ir a la universidad, el vaquero Woody, el astronauta Buzz […]',
    rating: '4.24',
    duration: '1h 40m',
    director: [ 'Andrew Cadelago', 'Lee Unkrich', 'Mark Sanford' ],
    genres: [ 'Animación', 'Aventura', 'Comedia' ],
    cast: [ 'Adam Joshua Jastrow', 'Amber Kroner', 'Aramé Scott' ]
  },
  ...
]
```

## 🚩 getLinks(id)
Returns a list of links of selected movie or episode of serie, using `id`.

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getLinks('21711/joker')
  .then((res) => console.log(res));
```

Results:
```json
  [
  {
    latino: [
      {
        url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4N1ZUN3ErYUhaV1IxYjBjcDI5MjRlWGo5OG1lb1JpZ0FWWFU1RFNyUEkvcDRDTDZOWGJhMUEzWTBRaUt6VmhuSTMrbUYvVG05b01rZFNkNEZiaGFnL3NtZlEyMDB5QUl0WnM2TXpibmJ4dWh3PT0'
      },
      ...
    ],
    espanol: [
      {
        url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4NVlpdllSTVEvMXRSam00M3N1TkJMSXJhaHpvVGVuZjVtdzVUN0NDTWJsQW9YTldwamIzN3dIbFlzTzFyMUY5UUlKdFNiaklWR2dCeWpaeFpNSTlId0hVWCtVeW93a0N2VCs5Nk9uZXRoMndRPT0'
      },
      ...
    ],
    sub: [
      {
        url: 'https://api.cuevana3.io/ir/goto_ddh.php?h=cHdlSGU2VjczUUVPODNNUXI0UWVpTEk3SGFLbjZaWUNQdStvVGEzUGc4NVZvR3BFTXY5NFI3TXpwUHVldVJyVHFQSmpMOVdYeGxGbFFDditCSDdZNnYrak4yL0lDTFJkU3oxZ1NaR2ZNU3NxRS81SnBMWUV4ZHBtSVA4b0s1MldIbXBXcTNPRENiMlJoZGdJNG5uNmNBPT0'
      },
      ...
    ]
  }
]
```

## 🚩 getDownload(id)
Returns a list of download links of selected movie or episode of serie, using `id`.

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getDownload('21711/joker')
  .then((res) => console.log(res));
```

Results:
```json
[
  {
    server: 'Uptobox',
    language: 'Latino',
    quality: 'HD',
    link: 'https://api.cuevana3.io/uptobox/goto.php?h=RTJjRkp0QUkwVUk3amU1Z01NU2tobnFFQmhEWFZYT3RzKzlrMXppYWpUamdLVEVEbW04aE9Fb3lVcmhYQUhrTw'
  },
  {
    server: 'Uptobox',
    language: 'Subtitulado',
    quality: 'HD',
    link: 'https://api.cuevana3.io/uptobox/goto.php?h=RTJjRkp0QUkwVUk3amU1Z01NU2todUZFdzRpMkw2WGJpdWlsNXYvSmt2RkhtSThYa3NuS25nQ0pJSFNrSTFUWQ'
  },
  {
    server: 'Uptobox',
    language: 'Español',
    quality: 'HD',
    link: 'https://api.cuevana3.io/uptobox/goto.php?h=RTJjRkp0QUkwVUk3amU1Z01NU2tobGRQUHZhYW4vUGp0QkVpYmkxOEthM2U1ajRQTVZhUXF4QXVabzRzN1M0UQ'
  }
]
```

## 🚩 getTrailer(id)
Returns a trailer link of selected movie/serie, using `id`.

Example:
```js
const cuevana3 = require('cuevana3');

cuevana3.getTrailer('21711/joker')
  .then((res) => console.log(res));
```

Results:
```json
[ 
  { 
    url: 'https://www.youtube.com/embed/UEpPggajCVQ' 
  }
]
``` 
---

### **:busts_in_silhouette: Credits**

- [Carlos Fernández](https://github.com/carlosfdezb) (Project Leader, and Developer)

---

### **:anger: Troubleshootings**

This is just a personal project created for study / demonstration purpose and to simplify my working life, it may or may
not be a good fit for your project(s).

---

### **:heart: Show your support**

Please :star: this repository if you like it or this project helped you!\
Feel free to open issues or submit pull-requests to help me improving my work.


---


### **:robot: Author**

_*Carlos Fernández*_

> You can follow me on
[github](https://github.com/carlosfdezb)

---

Copyright © 2021 [Cuevana3 Scraper](https://github.com/carlosfdezb/cuevana3).

<p align="center">
  <a href="http://forthebadge.com/" target="_blank">
    <img src="http://forthebadge.com/images/badges/built-with-love.svg"/>
  </a>
</p>

