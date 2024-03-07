<template>
  <div class="container">
    <div class="poem">
      <div class="controls">
        <button
          v-for="(_, index) in quatrains"
          :key="index"
          @click="toggleQuatrain(index)"
          :class="{ active: activeButtons.includes(index) }"
        ></button>
      </div>
      <div class="poem__body">
        <div class="flex-container">
          <h1>Invictus</h1>
          <span>By William Ernest Henley</span>
        </div>
        <div
          v-for="(quatrain, index) in quatrains"
          :key="index"
          class="quatrain"
          :class="{ hidden: activeButtons.includes(index) }"
        >
          <p v-for="(line, lineIndex) in quatrain" :key="lineIndex">{{ line }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      activeButtons: [],
      quatrains: [
        [
          "Out of the night that covers me,",
          "Black as the pit from pole to pole,",
          "I thank whatever gods may be",
          "For my unconquerable soul.",
        ],
        [
          "In the fell clutch of circumstance",
          "I have not winced nor cried aloud.",
          "Under the bludgeoning of chance",
          "My head is bloody, but unbowed.",
        ],
        [
          "Beyond this place of wrath and tears",
          "Looms but the Horror of the shade,",
          "And yet the menace of the years",
          "Finds and shall find me unafraid.",
        ],
        [
          "It matters not how strait the gate,",
          "How charged with punishments the scroll,",
          "I am the master of my fate,",
          "I am the captain of my soul.",
        ],
        [
          "Out of the night that covers me,",
          "Black as the pit from pole to pole,",
          "I thank whatever gods may be",
          "For my unconquerable soul.",
        ],
        [
          "Out of the night that covers me,",
          "Black as the pit from pole to pole,",
          "I thank whatever gods may be",
          "For my unconquerable soul.",
        ],
      ],
    };
  },

  methods: {
    toggleQuatrain(i) {
      if (this.activeButtons.includes(i)) {
        this.activeButtons = this.activeButtons.filter((button) => button !== i);
      } else if (this.activeButtons.length < 3) {
        this.activeButtons = [...this.activeButtons, i];
      }
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}
.hidden {
  display: none;
}
.poem {
  display: flex;
  margin: 0 auto;
  max-width: 1200px;
}
.controls {
  display: flex;
  column-gap: 25px;
  max-width: 600px;
  padding-top: 12.5%;
  margin-right: 30px;
}
button {
  width: 25px;
  height: 25px;
  background-color: #000;
  outline: none;
  border: none;
  cursor: pointer;
  transition: 0.2s ease;
}
button.active {
  border: 2px solid black;
  background-color: transparent;
}

h1 {
  font-weight: 500;
  padding-left: 7%;
}
p {
  margin: 0;
}
p:nth-child(even) {
  padding-left: 50px;
}

p:nth-child(odd) {
  padding-right: 50px;
}

.poem__body {
  width: 100%;
  min-width: 1600px;
  font-size: 1.2rem;
  margin: 0 auto;
}
.quatrain {
  margin-bottom: 15px;
}
.flex-container {
  display: flex;
  align-items: center;
  column-gap: 70px;
}
.flex-container span {
  margin: 0;
  padding: 0;
}
html {
  font-size: 16px;
}

@media screen and (min-width: 799.8px) {
  h1 {
    padding-left: 85px;
  }
  .container {
    max-width: 1000px;
  }
  .flex-container {
    column-gap: 20px;
  }
  .poem {
    margin: 0;
  }
  .controls {
    padding-top: 91px;
    margin-right: 10px;
  }
  .poem__body {
    min-width: 500px;
  }
}

/* Настройка размера текста для экранов шириной до 8000px */

/* Дополнительные настройки размера текста для других размеров экрана */
@media screen and (min-width: 1600px) {
  html {
    font-size: 24px;
  }
  .controls {
    padding-top: 15.5%;
    margin-right: 25px;
  }
  .flex-container {
    column-gap: 70px;
  }
}
@media screen and (min-width: 2400px) {
  .container {
    max-width: 1600px;
  }
  html {
    font-size: 34px;
  }
  .controls {
    padding-top: 18.5%;
    margin-right: 30px;
  }
}
@media screen and (min-width: 3600px) {
  .container {
    max-width: 2200px;
  }
  html {
    font-size: 38px;
  }
  button {
    width: 38px;
    height: 38px;
  }
  .controls {
    padding-top: 19.5%;
    column-gap: 38px;
  }
}

@media screen and (min-width: 4600px) {
  .container {
    max-width: 3200px;
  }
  html {
    font-size: 48px;
  }
  button {
    width: 48px;
    height: 48px;
  }
  .controls {
    padding-top: 24.5%;
    column-gap: 48px;
    margin-right: 40px;
  }
  .poem__body {
    min-width: 1500px;
  }
}
@media screen and (min-width: 5600px) {
  html {
    font-size: 52px;
  }
  button {
    width: 52px;
    height: 52px;
  }
  .controls {
    column-gap: 52px;
    padding-top: 26.5%;
    margin-right: 60px;
  }
}
@media screen and (min-width: 6600px) {
  html {
    font-size: 58px;
  }
  button {
    width: 58px;
    height: 58px;
  }
  .controls {
    padding-top: 28.5%;
    column-gap: 58px;
  }
}
@media screen and (min-width: 7600px) {
  .container {
    max-width: 2800px;
  }
  html {
    font-size: 72px;
  }
  .controls {
    padding-top: 37.5%;
    column-gap: 72px;
  }
  button {
    width: 72px;
    height: 72px;
  }
  .poem__body {
    min-width: 2000px;
  }
}
</style>
