<template>
  <v-app>
    <v-main class="dogs-layout">
      <v-container fill-height>
        <div class="dogs-overlay">
          <h1 class="display-2 text-xs-center">
            <button class="bone" @click="loadNewDog">
              <div class="c1"></div>
              <div class="c2"></div>
              <div class="c3"></div>
              <div class="c4"></div>
              <div class="b1">
                <div class="b2">DOGS !</div>
              </div>
            </button>
          </h1>
          <b-row align-v="center">
            <app-dog :dog="currentDogLinkArray[0]"></app-dog>
            <app-dog :dog="currentDogLinkArray[1]"></app-dog>
            <app-dog :dog="currentDogLinkArray[2]"></app-dog>
            <app-dog :dog="currentDogLinkArray[3]"></app-dog>
            <app-dog :dog="currentDogLinkArray[4]"></app-dog>
            <app-dog :dog="currentDogLinkArray[5]"></app-dog>
            <app-dog :dog="currentDogLinkArray[6]"></app-dog>
            <app-dog :dog="currentDogLinkArray[7]"></app-dog>
            <app-dog :dog="currentDogLinkArray[8]"></app-dog>
            <app-dog :dog="currentDogLinkArray[9]"></app-dog>
            <app-dog :dog="currentDogLinkArray[10]"></app-dog>
            <app-dog :dog="currentDogLinkArray[11]"></app-dog>
            <app-dog :dog="currentDogLinkArray[12]"></app-dog>
            <app-dog :dog="currentDogLinkArray[13]"></app-dog>
            <app-dog :dog="currentDogLinkArray[14]"></app-dog>
            <app-dog :dog="currentDogLinkArray[15]"></app-dog>
            <app-dog :dog="currentDogLinkArray[16]"></app-dog>
            <app-dog :dog="currentDogLinkArray[17]"></app-dog>
            <app-dog :dog="currentDogLinkArray[18]"></app-dog>
            <app-dog :dog="currentDogLinkArray[19]"></app-dog>
          </b-row>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";
import DogCard from "./components/DogCard";

export default {
  components: {
    appDog: DogCard,
  },
  data() {
    return {
      currentDogLink: "",
      currentDogLinkArray: [],
    };
  },
  methods: {
    loadNewDog() {
      this.currentDogLink = "";
      axios
        .get("https://dog.ceo/api/breeds/image/random/20")
        .then((response) => {
          this.currentDogLinkArray = response.data.message;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.loadNewDog();
  },
};
</script>

<style lang="scss">
img {
  max-width: 100%;
}

h1 {
  padding-bottom: 15px;
}

.dogs-layout {
  width: 100%;
  background: #fff center repeat;
  background-image: url("https://www.seekpng.com/png/detail/42-426149_about-us-dog-paw-background-png.png");
}

.dogs-overlay {
  width: 100%;
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

@media (max-width: 768px) {
  .dogs-overlay {
    margin: 0;
  }
}

.dog-card {
  width: 100%;
  height: 350px;
  max-width: 600px;
  background-color: #ebedeb;
  margin: 22px;
  padding: 5%;
}

.bone {
  margin-top: 40px;
  margin-bottom: 40px;
  position: relative;
  width: 600px;
  height: 100px;
  cursor: pointer;
  background: transparent;
  border: none;
}
.c1,
.c2,
.c3,
.c4 {
  background: #e6d15a;
  height: 67px;
  width: 67px;
  border-radius: 50%;
  position: absolute;
}
.c1 {
  left: 0;
  top: 0;
}
.c2 {
  right: 0;
  top: 0;
}
.c3 {
  left: 0;
  bottom: 0;
}
.c4 {
  bottom: 0;
  right: 0;
}
.b1 {
  background: #e6d15a;
  height: 70px;
  width: 570px;
  position: absolute;
  left: 15px;
  top: 15px;
}
.b2 {
  position: absolute;
  left: 15px;
  top: 0;
  width: 500px;
  height: 70px;
  line-height: 30px;
  text-align: center;
  padding-top: 20px;
  font-family: fantasy;
  font-size: 35px;
  font-style: normal;
  font-variant: normal;
  font-weight: 500;
  line-height: 26.4px;
}
</style>
