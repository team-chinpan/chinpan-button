<template>
  <div class='top'>
    <section class='top__main'>
      <p>{{ topInfo.emoji }}</p>
      <h1>{{ topInfo.title }}</h1>
    </section>
    <section class='top__form'>
      <p>{{ formInfo.description }}</p>
      <button>レッツ チンパン👉</button>
      <p class='top__form__error'>{{ formInfo.error.notChinpan }}</p>
    </section>
    <section class='top__successive'>
      <div class='top__successive__title'>
        <p>🎓</p>
        <h1>歴代チンパニスト</h1>
      </div>
      <ul class='top__successive__content'>
        <li v-for='(chinpanist, index) in chinpanistInfo' :key='chinpanist.id'>
          <div>
            <h3>{{ index + 1 + '. ' + chinpanist.name }}</h3>
            <h5>@{{ chinpanist.id }}</h5>
            <p>就任日: {{ chinpanist.created }}</p>
          </div>
        </li>
        <li class='top__successive__content__notfound'>
          <p>まだチンパンになった人はいません</p>
        </li>
      </ul>
    </section>
    <section class='top__link'>
      <div class='top__link__title'>
        <p>🔗</p>
        <h1>リンク</h1>
      </div>
      <ul class='top__link__content'>
        <li v-for='link in linkInfo' :key='link.id'>
          <a :href='link.url'>
            <p>{{ link.emoji }}</p>
            <h3>{{ link.title }}</h3>
          </a>
        </li>
      </ul>
    </section>
    <section class='top__credit'>
      <div class='top__credit__title'>
        <p>📕</p>
        <h1>クレジット</h1>
      </div>
      <div class='top__credit__content'>
        <p>{{ credit }}</p>
      </div>
    </section>
    <div class='top__cr'>©︎ 2021 chinpan</div>
  </div>
</template>

<script lang='ts'>
import Vue from 'vue';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default Vue.extend({
  data() {
    return {
      topInfo: {
        title: 'チンパンボタン',
        emoji: '🙈',
      },
      formInfo: {
        description: 'ボタンを押すとあなたがチンパンかどうか分かるよ‼️とりあえず一発押してみよう👊',
        error: {
          notChinpan: '残念..あなたはチンパンじゃないみたい🤦‍♀️',
        },
      },
      chinpanistInfo: [],
      linkInfo: [
        {
          title: 'Github',
          emoji: '🐱',
          url: 'https://github.com/team-chinpan/chinpan-button',
        },
      ],
      credit: 'Twemoji graphics licensed under CC-BY 4.0.',
    };
  },
});
</script>

<style lang='scss'>
.top {
  padding: 80px 0;
  max-width: 330px;
  display: flex;
  flex-direction: column;;
  min-height: 100vh;
  margin: 0 auto;
}

.top__main {
  display: flex;
  justify-content: center;
  align-items: center;
      text-shadow:
      black 2px 0px,  black -2px 0px,
      black 0px -2px, black 0px 2px,
      black 2px 2px , black -2px 2px,
      black 2px -2px, black -2px -2px,
      black 1px 2px,  black -1px 2px,
      black 1px -2px, black -1px -2px,
      black 2px 1px,  black -2px 1px,
      black 2px -1px, black -2px -1px;
  h1 {
    font-family: vdl-logojrblack, sans-serif;
    font-weight: 900;
    font-style: normal;
    font-size: 32px;
    letter-spacing: 6px;
    color: #fff;
  }
  p {
    font-size: 45px;
    margin-right: 15px;
  }
}

.top__form {
  background-color: #fff;
  padding: 15px;
  border-radius: 8px;
  border: 3px solid #000;
  font-size: 12px;
  max-width: 350px;
  text-align: center;
  margin: 0 auto;
  button {
    font-family: vdl-logojrblack, sans-serif;
    font-weight: 900;
    font-style: normal;
    margin-top: 15px;
    letter-spacing: 2px;
    color: #fff;
    background-color: rgb(255, 74, 98);
    border: 3px solid rgb(255, 68, 93);
    border-radius: 30px;
    padding: 8px 12px;
  }
}

.top__form__error {
  font-size: 10px;
  margin-top: 15px;
  color: rgb(255, 74, 98);
}

.top__successive {
  margin-top: 20px;
}

.top__successive__title {
  display: flex;
  align-items: center;
      text-shadow:
      black 2px 0px,  black -2px 0px,
      black 0px -2px, black 0px 2px,
      black 2px 2px , black -2px 2px,
      black 2px -2px, black -2px -2px,
      black 1px 2px,  black -1px 2px,
      black 1px -2px, black -1px -2px,
      black 2px 1px,  black -2px 1px,
      black 2px -1px, black -2px -1px;
  h1 {
    font-family: vdl-logojrblack, sans-serif;
    font-weight: 900;
    font-style: normal;
    font-size: 20px;
    letter-spacing: 6px;
    color: #fff;
  }
  p {
    font-size: 28px;
    margin-right: 15px;
  }
}

.top__successive__content li {
  margin-top: 5px;
}

.top__successive__content li:first-child {
  margin-top: 0;
}

.top__successive__content li div {
  background-color: #fff;
  padding: 10px;
  border: 3px solid #000;
  border-radius: 8px;
  width: 100%;
}

.top__successive__content li div h3 {
  font-size: 16px;
}

.top__successive__content li div h5 {
  font-size: 14px;
  color: rgb(88, 88, 88);
}

.top__successive__content li div p {
  font-size: 10px;
}

.top__successive__content__notfound {
  padding: 10px;
  border: 3px solid #000;
  border-radius: 8px;
  width: 100%;
  font-size: 12px;
  background-color: #fff;
}

.top__link {
  margin-top: 20px;
}

.top__link__title {
  display: flex;
  align-items: center;
      text-shadow:
      black 2px 0px,  black -2px 0px,
      black 0px -2px, black 0px 2px,
      black 2px 2px , black -2px 2px,
      black 2px -2px, black -2px -2px,
      black 1px 2px,  black -1px 2px,
      black 1px -2px, black -1px -2px,
      black 2px 1px,  black -2px 1px,
      black 2px -1px, black -2px -1px;
  h1 {
    font-family: vdl-logojrblack, sans-serif;
    font-weight: 900;
    font-style: normal;
    font-size: 20px;
    letter-spacing: 6px;
    color: #fff;
  }
  p {
    font-size: 28px;
    margin-right: 15px;
  }
}

.top__link__content li {
  margin-top: 5px;
}

.top__link__content li:first-child {
  margin-top: 0;
}

.top__link__content li a {
  display: flex;
  align-items: center;
  background-color: #fff;
  border: 3px solid #000;
  border-radius: 8px;
  padding: 10px;
  width: 100%;
  p {
    font-size: 16px;
    margin-right: 10px;
    align-items: center;
    text-shadow:
      black 1px 1px 0, black -1px -1px 0,
      black -1px 1px 0, black 1px -1px 0,
      black 0px 1px 0, black  0-1px 0,
      black -1px 0 0, black 1px 0 0;
  }
  h3 {
    font-size: 12px;
  }
}

.top__credit {
  margin-top: 20px;
}

.top__credit__title {
  display: flex;
  align-items: center;
      text-shadow:
      black 2px 0px,  black -2px 0px,
      black 0px -2px, black 0px 2px,
      black 2px 2px , black -2px 2px,
      black 2px -2px, black -2px -2px,
      black 1px 2px,  black -1px 2px,
      black 1px -2px, black -1px -2px,
      black 2px 1px,  black -2px 1px,
      black 2px -1px, black -2px -1px;
  h1 {
    font-family: vdl-logojrblack, sans-serif;
    font-weight: 900;
    font-style: normal;
    font-size: 20px;
    letter-spacing: 6px;
    color: #fff;
  }
  p {
    font-size: 28px;
    margin-right: 15px;
  }
}

.top__credit__content {
  background-color: #fff;
  border: 3px solid #000;
  border-radius: 8px;
  padding: 10px;
  width: 100%;
  font-size: 12px;
}

.top__cr {
  font-size: 10px;
  width: 120px;
  padding: 5px 0;
  margin: 100px auto 0;
  text-align: center;
  background-color: #fff;
  border: 2px solid #000;
  border-radius: 30px;
}
</style>
