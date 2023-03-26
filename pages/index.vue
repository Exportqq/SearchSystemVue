<template>
  <div>
    <div>
      <ul>
        <li>
          <input class="search" type="search" v-model="search" placeholder="Поиск фильма"/>
        </li>
      </ul>
      <ul v-if="search.length">
        <li class="serch_line" v-for="item in serchHandler" :key="item.id">
          <a v-bind:href="item.url">
            <div class="search-rectangle">
              <ul class="search-list">
                <li>
                  <img :src="item.img">
                </li>
                <li>
                  <a class="serch-txt">{{ item.name }}</a>
                  <p class="film-genre">{{ item.title }}</p>
                </li>
                <li>
                  <p class="age-limit">{{ item.age }}</p>
                </li>
              </ul>
            </div>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [
      {
        name: "Человек-паук: Нет пути домой (2021)",
        url: "https://www.kinopoisk.ru/film/1309570/",
        img: "pauk.png",
        title: "Жанр: фантастика, приключения, фэнтези",
        age: "12+"
      },
      {
        name: "Человек-муравей и Оса: Квантомания (2023)",
        url: "https://www.kinopoisk.ru/film/1318868/",
        img: "muravey.png",
        title: "Жанр: фантастика, боевик, комедия, приключения",
        age: "16+"
      },
      {
        name: "Чебурашка (2022)",
        url: "https://www.kinopoisk.ru/film/4370148/",
        img: "cheburashka.png",
        title: "Жанр: семейный, комедия",
        age: "6+"
      },
      ],
      search: ""
    }
  },
  computed: {
    serchHandler() {
      return this.data.filter(elem => {
        return elem.name.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  },
}
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
}

ul li {
  list-style: none;
}

.film-genre {
  width: 420px;
  height: 98px;
  font-family: 'Montserrat', sans-serif;
  padding: 40px 0px 0px 24px;
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 29px;
  color: #000000;
}

.serch_line {
  width: 669px;
}

.search {
  width: 669px;
  height: 100px;
  background: #FFFFFF;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.25);
  border-radius: 30px;
  font-family: 'Inter', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 40px;
  line-height: 48px;
  text-indent: 45px;
  border: 1px solid #000;
  background: url(static/magnifying.svg) no-repeat 554px;
  transition: 0.4s;
}

:active, :hover, :focus {
    outline: 0;
    outline-offset: 0;
}

.search:focus {
  width: 669px;
  height: 100px;
  background: #FFFFFF;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.25);
  border-radius: 30px;
  font-family: 'Inter', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 40px;
  line-height: 48px;
  text-indent: 45px;
  border: 4px solid #000;
  background: url(static/magnifying.svg) no-repeat 700px;
}

.search-list li {
  float: left;
}

.serch-txt {
  width: 437px;
  height: 78px;
  font-family: 'Montserrat', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 32px;
  line-height: 39px;
  color: #000000;
  display:inline-block;
  padding: 20px 0px 0px 24px;
  }

.search-rectangle {
  width: 669px;
  margin-top: 15px;
  height: 216px;
  background: #FFFFFF;
  box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.25);
  border-radius: 5px;
}

.age-limit {
  width: 52px;
  height: 39px;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  margin: 157px 0px 0px 6px;
  font-style: normal;
  font-weight: 600;
  font-size: 32px;
  line-height: 39px;
  color: #6AAE59;
}
</style>

</script>
