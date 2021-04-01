<template>
  <div class="about" id="about">
    <h1>VS</h1>
    <div class="show" id="show" v-if="show_grid">
      <div
        id="left"
        class="left"
        v-on:click="
          left();
          save();
        "
      >
        <img id="img__left" :src="currentPair.img1" />
      </div>
      <div
        id="right"
        class="right"
        @click="
          right();
          save();
        "
      >
        <img id="img__right" :src="currentPair.img2" />
      </div>
    </div>
    <div class="grid" v-else>
      <h1>vin</h1>
      <div id="left" class="left">
        <img id="img__left" :src="currentPair.img1" />
      </div>
      <div class="grid_2">
        <div class="img" v-for="img in mass_2" :key="img">
          <img :src="img" alt="" />
        </div>
      </div>
      <br />
      <div class="grid_4">
        <div class="img" v-for="img in mass_4" :key="img">
          <img :src="img" alt="" />
        </div>
      </div>
      <br />
      <div class="grid_8">
        <div class="img" v-for="img in mass_8" :key="img">
          <img :src="img" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Table",
  props: {
    msg: String,
  },
  data: function () {
    return {
      dogs: [
        "https://bipbap.ru/wp-content/uploads/2017/10/07_06_2017_10_08_15_jijtj2ru3nraq07t0u7a9degh0_war6mice03.jpg",
        "https://bipbap.ru/wp-content/uploads/2017/10/00115b52c3100b01ac0a0b.jpg",
        "https://milota.online/storage/posts/January2019/TDu3BrpBSNNwy0pzTba3.jpg",
        "https://milota.online/storage/posts/January2019/velsh-korgi.jpg",
        "https://milota.online/storage/posts/January2019/kavaler-spaniel.jpg",
        "https://milota.online/storage/posts/January2019/veymarskaya-legavaya.jpg",
        "https://milota.online/storage/posts/January2019/milaya-haski.jpg",
        "https://milota.online/storage/posts/January2019/miliy-york.jpg",
        "https://images11.popmeh.ru/upload/img_cache/a31/a31231f224e1df77d915693886df424d_cropped_666x412.webp?webp",
        "https://images11.popmeh.ru/upload/img_cache/84b/84b53cf4a80aa15e9ffb86fc968c8939_cropped_666x414.webp?webp",
        "https://images11.popmeh.ru/upload/img_cache/e75/e75424310a1f0b0f2a30f6c70776e70c_cropped_666x355.webp?webp",
        "https://www.sobaka.ru/images/image/01/18/55/25/_normal.jpg",
        "https://ru.mypetandi.com/sites/g/files/adhwdz671/files/styles/paragraph_image/public/2020-04/small-dog-grass.jpg?itok=skKvamJG",
        "https://porodu-sobak.ru/wp-content/uploads/2018/06/samoyed16.jpg",
      ],
      mass: [],
      mass_8: [],
      mass_4: [],
      mass_2: [],
      show_grid: true,
      index: 0,
      currentPair: {
        img1:
          "https://cs4.pikabu.ru/post_img/2014/03/19/10/1395243232_1089834701.jpg",
        img2:
          "https://img4.goodfon.ru/wallpaper/nbig/8/70/shchenok-sobachka-boke-kappa-mylnyi-puzyr.jpg",
      },
    };
  },
  created() {
    setTimeout(() => {
      this.$emit("test", 12);
    }, 5000);
  },
  // mounted() {
  // },
  methods: {
    save() {
      if (this.index < this.dogs.length) {
        this.currentPair.img1 = this.dogs[this.index];
        this.currentPair.img2 = this.dogs[this.index + 1];
        this.index = this.index + 2;
      } else {
        if (this.mass.length == 8) {
          this.mass_8 = this.mass;
          this.dogs = this.mass;
          this.mass = [];
          this.index = 0;
          this.currentPair.img1 = this.dogs[this.index];
          this.currentPair.img2 = this.dogs[this.index + 1];
          this.index = this.index + 2;
          console.log("ну типа конец на 8");
          //рабочая схема
        }
        if (this.mass.length == 4) {
          this.mass_4 = this.mass;
          this.dogs = this.mass;
          this.mass = [];
          this.index = 0;
          this.currentPair.img1 = this.dogs[this.index];
          this.currentPair.img2 = this.dogs[this.index + 1];
          this.index = this.index + 2;
          console.log("ну типа конец на 4");
        }
        if (this.mass.length == 2) {
          this.mass_2 = this.mass;
          this.dogs = this.mass;
          this.mass = [];
          this.index = 0;
          this.currentPair.img1 = this.dogs[this.index];
          this.currentPair.img2 = this.dogs[this.index + 1];
          this.index = this.index + 2;
          console.log("ну типа конец на 2");
        }
        if (this.mass.length == 1) {
          this.mass_2 = this.mass;
          this.dogs = this.mass;
          this.mass = [];
          this.index = 0;
          this.currentPair.img1 = this.dogs[this.index];
          this.currentPair.img2 = this.dogs[this.index];
          console.log("vin");
          this.grid();
        }
      }
    },
    left: function () {
      this.mass.push(this.currentPair.img1);
    },
    right: function () {
      this.mass.push(this.currentPair.img2);
    },
    grid: function () {
      this.show_grid = false;
    },
    grid_img: function (img) {
      console.log(img);
      return (document.createElement("img").src = img);
    },
  },
};
</script>

<style scoped>
.show {
  display: flex;
  height: 50vh;
}
.right {
  width: 50%;
  height: 100%;
}
.right img,
.left img {
  width: 100%;
}
.left {
  color: #fff;
  width: 50%;
  height: 100%;
}
.grid_8,
.grid_4,
.grid_2 {
  display: flex;
  height: 100px;
}
.img img {
  height: 80px;
  width: 80px;
}
</style>
