<template>
  <div class="home">
    <img alt="Game logo" src="../assets/logo.png">
    <h3>Choose your option to start playing</h3>
    <p>One chance only, you either win or loose!</p>
    <form @submit.prevent="sendUserSelection">
      <radio-button class="radio-button"
        v-for="(choice, index) in choices"
        :key="index"
        :value="choice"
        required
        name="choice"
      />
      <br>
      <the-button class="the-button"
        type="submit"
        text="Play!"
      />
    </form>
    <result
      v-if="showResult"
      :result="isUserWinner"
    />
    <ErrorMessage />
  </div>
</template>

<script>
// @ is an alias to /src
import { mapGetters, mapActions } from 'vuex';
import RadioButton from '@/components/RadioButton.vue';
import TheButton from '@/components/TheButton.vue';
import Result from '@/components/Result.vue';
import ErrorMessage from '@/components/ErrorMessage.vue';

export default {
  name: 'home',
  components: {
    RadioButton,
    TheButton,
    Result,
    ErrorMessage,
  },
  computed: {
    ...mapGetters([
      'choices',
      'showResult',
      'isUserWinner',
    ]),
  },
  methods: {
    ...mapActions([
      'playGame',
    ]),
    sendUserSelection() {
      const userSel = this.$el.querySelector('.radio:checked');
      // userSel != null ? this.playGame(userSel) : this.playGame("empty");
      if (userSel != null) {
        this.playGame(userSel.value);
      } else {
        this.playGame('empty');
      }
    },
  },
};
</script>


<style lang="scss" scoped>

.home{
  position: fixed;
  top: 50%;
  left: 50%;
  width: 100wv;
  transform: translate(-50%, -50%);

  img{
    width: 400px;
    height: 300px;
  }

  form{
    padding:30px;

    .radio-button{
      margin:5px;
    }

    .the-button{
      margin-top:40px;
    }
  }

  p{
    font-size: 0.9em;
  }

  h3{
    margin-top: 0;
    margin-bottom: 0;
  }
}


@media (min-width: 768px) and (max-width: 1023px) {
  //Tablet
.home{
   width: 40em;
   height: 40em;
  }
}

@media (min-width: 1024px) {
  //Desktop
.home{
   width: 40em;
   height: 45em;

  img{
    width: 500px;
    height: 375px;
  }
  }
}
</style>
