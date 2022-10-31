<template>
  <section>
    <div class="container" v-for="slip in slip" v-bind:key="slip.id">
      <div v-if="slip">
        <p class="adviceid">ADVICE # <span class="slipid">{{ slip.id }}</span></p>

        <p class="quote">"{{ slip.advice }}"</p>
      </div>
      <div v-else-if="!slip">
        <H1>loading</H1>
      </div>
      <div class="bottom">
        <img class="divider" src="../assets/pattern-divider-desktop.svg" />
        <button class="roll" @click="newAdvice(); disableButton();" :disabled="isDisabled">
          <img
            src="../assets/icon-dice.svg"
            alt=""
            id="dice"
          />
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      slip: null,
      isDisabled: false,
    };
  },
  methods: {
    refresh() {
      this.$router.go(this.$router.currentRoute);
    },
    newAdvice() {
      fetch("	https://api.adviceslip.com/advice", {})
        .then((res) => res.json())
        .then((data) => (this.slip = data), console.log(this.slip));
        
    },
     disableButton() {
       this.isDisabled = true;
       setTimeout(() => this.isDisabled = false, 3000);
            console.error('3s cooldown on button')
     },
    
  },

  mounted() {
    this.newAdvice();
  },
};
</script>
<style>
section {
  width: 100%;
  height: 100vh;
  background: var(--dblue);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Manrope", sans-serif;
  font-weight: 800;
}
.container {
  width: 40rem;
  height: 22rem;
  background: var(--dgblue);
  border-radius: 15px;
  display: flex;
  align-items: center;
  padding-top: 3rem;
  padding-left: 3rem;
  padding-right: 3rem;
  flex-direction: column;
}
.advice {
}
.adviceid {
  width: 100%;
  text-align: center;
  color: var(--neong);
  letter-spacing: 3px;
  font-weight: 700;
  padding-bottom: 1rem;
}
.quote {
  font-size: 28px;
  color: var(--lcyan);
  width: 100%;
  text-align: center;
  animation: drop-in .5s ease-in-out;
}
.divider {
  padding-top: 3rem;
}
.hide {
  display: none;
}
.roll {
  background: var(--neong);
  border: none;
  padding: 1.5rem;
  border-radius: 50%;
  width: fit-content;
  height: fit-content;
  margin-top: 2.3rem;
  transition: 0.4s ease all;
}
.roll:disabled{
   background: var(--gblue);
   box-shadow: none;

}

#dice{
  scale: 1.1;
}
.roll:hover:enabled {
  box-shadow: 0px 0px 24px 0px var(--neong);
}
.roll:hover #dice {
  scale: 1.1;
}
.roll:focus #dice {
  animation: spin 1s linear;  
}
.roll:Focus{
scale: 1.1;
}
@keyframes spin {
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
    top: -10px;
  }
}
@keyframes drop-in{
  0%{
    translate: 0px -100px;
    text-shadow: 20px 20px 0px black;
    opacity: 0;

  }
  100%{
    translate: 0px 0px;
    text-shadow: none;
    opacity: 1;
  }
}
.bottom {
  position: absolute;
  translate: 0px 10.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.slipid{
  
}
</style>
