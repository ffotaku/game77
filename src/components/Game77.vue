<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-sm">
        <div id="ff">
          {{aplayer.name}}
          {{aplayer.hp}}
          </div>
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <img style="width:100%" :src="aplayer.img" />
        </div>
        <div class="col-sm">
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <button v-bind:disabled="end" @click="start()" class="btn btn-dark ml-2">Start</button>
          <button v-bind:disabled="end" @click="attack()" class="btn btn-dark ml-2">Attack</button>
          <button v-bind:disabled="end" @click="special()" class="btn btn-dark ml-2">Special Attack</button>
          <br />
          <br />
          <button @click="reset()" class="btn btn-dark ml-2">New game</button>
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <img style="width:80%" src="https://media3.giphy.com/media/TiJfX5nRSnvshdijyb/source.gif" />
          <br />
          <br />
          <br />
          <div id="ff">
          <div v-if="amonster.hp <= 0">You Win</div>
          <div v-else-if="aplayer.hp <= 0">You Lose</div>
          </div>
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
        </div>
        <div class="col-sm">
        <div id="ff">
          {{amonster.name}}
          {{amonster.hp}}
          </div>
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <br />
          <img style="width:100%" :src="amonster.img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      aplayer: { name: "", hp: 0, img: "" },
      playmax: "",
      monsmax: "",
      end: false,
      player: [
        {
          name: "Soldier 76",
          hp: 100,
          img:
            "https://i.pinimg.com/originals/70/22/fc/7022fcf140138735d02273d4c31acdcf.gif?fbclid=IwAR21syBTc6DfyOB65xY0khSc571ITE0Qvq6drlwlGphYi0l_ECeIoD9ZkHQ",
        },
        {
          name: "Iron man",
          hp: 120,
          img:
            "https://i.pinimg.com/originals/9e/06/97/9e0697990828bb8319be8105c939b108.gif?fbclid=IwAR1V9uF8iYmxkBACYJ2G2-S6_-SYVfwcbF1_qFkASOIuyQKs80NE8myiknE",
        },
        {
          name: "Hulk",
          hp: 100,
          img: "https://www.fightersgeneration.com/characters/hulk-stance.gif",
        },
      ],

      amonster: { name: "", hp: 0, img: "" },
      monster: [
        {
          name: "Thanos",
          hp: 150,
          img:
            "https://thumbs.gfycat.com/DifferentNegativeEmeraldtreeskink-size_restricted.gif?fbclid=IwAR1MtWvW5fNGKfKu9UeAYmF7-ZXD7bmmchGNYhAghggReT0cqiEGdmFX4T4",
        },
        {
          name: "Windowmaker",
          hp: 80,
          img:
            "https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/i/43636789-6283-4cbf-b9a5-5edca38b9970/db578wf-24c1b6b6-98fc-4450-a980-f9023860cdfe.gif?fbclid=IwAR1MtWvW5fNGKfKu9UeAYmF7-ZXD7bmmchGNYhAghggReT0cqiEGdmFX4T4",
        },
        {
          name: "Loki",
          hp: 90,
          img: "https://66.media.tumblr.com/tumblr_maw5qzmzqp1rfjowdo1_500.gif",
        },
      ],
    };
  },
  methods: {
    random: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      //1.random player 1-3  ชื่อ hp รูป
      this.aplayer = this.player[this.random(1, 3) - 1];
      this.amonster = this.monster[this.random(1, 3) - 1];
    },
    attack: function () {
      this.playmax = this.random(1, 5);
      this.aplayer.hp = this.aplayer.hp - this.playmax;
      this.monsmax = this.random(1, 5);
      this.amonster.hp = this.amonster.hp - this.monsmax;
     if (this.aplayer.hp <= 0) {

        this.aplayer.hp = 0;

        this.end = true;

      } else if (this.amonster.hp <= 0) {

        this.amonster.hp = 0;

        this.end = true;

      }
    },
     special: function () {

      this.pmax = Math.floor(Math.random() * 15 + 6);

      this.amonster.hp = this.amonster.hp - this.pmax;

      this.mmax = Math.floor(Math.random() * 15 + 6);

      this.aplayer.hp = this.aplayer.hp - this.mmax;

      if (this.aplayer.hp <= 0) {

        this.aplayer.hp = 0;

        this.end = true;

      } else if (this.amonster.hp <= 0) {

        this.amonster.hp = 0;

        this.end = true;

      }

    },
      reset: function () {

      window.location.reload();

    },
  },
    
};
</script>

<style>
#ff{
  font-size: 50px;
}
</style>