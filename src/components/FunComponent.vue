<template>
  <div>
    <button class="button_one">click me</button>
    <section class="secret_container"></section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      secrets: [`one`, `two`, `three`],
    };
  },

  methods: {
    change_one() {
      document.body[`style`][`background`] = `blue`;
    },
  },

  mounted() {
    let button_one = document.querySelector(`.button_one`);
    button_one.addEventListener(`click`, this.change_one);
    let secret_container = document.querySelector(`.secret_container`);
    for (let i = 0; i < this.secrets.length; i++) {
      secret_container.insertAdjacentHTML(
        `beforeend`,
        `<p class="secrets">${this.secrets[i]}</p>`
      );
    }

// let secrets = document.getElementsByClassName(`secrets`);
// for (let i = 0; i < secrets.length; i++) {
//   secrets[i].addEventListener(`click`, )
// }
  },
};
</script>

<style scoped>
</style>