<template lang="html">
  <div>
    <section id="monster" class="container">
        <h2>Monster Health</h2>
        <div class="healthbar">
            <div class="healthbar__value"></div>
        </div>
    </section>
    <section id="player" class="container">
        <h2>Your Health</h2>
        <div class="healthbar">
            <div class="healthbar__value"></div>
        </div>
    </section>
    <section id="controls">
        <button>ATTACK</button>
        <button>SPECIAL ATTACK</button>
        <button>HEAL</button>
        <button>SURRENDER</button>
    </section>
    <section id="log" class="container">
        <h2>Battle Log</h2>
        <ul></ul>
    </section>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss">
  $color-black: #000;
  $color-blackLight: #3f3f3f;
  $color-gray: #ccc;
  $color-white: #fff;

  $color-red: #af0a78;
  $color-lightred: #ec3169;

  $color-primary: #880017;
  $color-secondary: #575757;
  $color-tertiary: #fde5e5;
  $color-health: #00a876;

  %boxStyling {
  text-align: center;
  padding: 0.5rem;
  box-shadow: 0 2px 8px rgba($color-black, 0.26);
  }

  * {
      box-sizing: border-box;
  }

  html {
      font-family: "Jost", sans-serif;
  }

  body {
      margin: 0;
  }

  header {
      @extend %boxStyling;
      background-color: $color-primary;
      color: $color-white;
      margin-bottom: 2rem;
  }

  section {
      width: 90%;
      max-width: 40rem;
      margin: auto;
  }

  .container {
      @extend %boxStyling;
      margin: 1rem auto;
      border-radius: 12px;
  }

  .healthbar {
      width: 100%;
      height: 40px;
      border: 1px solid $color-secondary;
      margin: 1rem 0;
      background: $color-tertiary;

  &__value {
      background-color: $color-health;
      width: 100%;
      height: 100%;
  }
  }

  #monster {
    h2 {
      margin: 0.25rem;
    }
  }

  #player {
    h2 {
      margin: 0.25rem;
    }
  }

  #controls {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
  }

  button {
    font: inherit;
    border: 1px solid $color-primary;
    background-color: $color-primary;
    color: $color-white;
    padding: 1rem 2rem;
    border-radius: 12px;
    margin: 1rem;
    width: 12rem;
    cursor: pointer;
    box-shadow: 1px 1px 4px rgba($color-black, 0.26);

    &:focus {
      outline: none;
    }

    &:hover,
    &:active {
      background-color: $color-red;
      border-color: $color-red;
      box-shadow: 1px 1px 8px rgba($color-black, 0.26);
    }

    &:disabled {
      background-color: $color-gray;
      border-color: $color-gray;
      box-shadow: none;
      color: $color-blackLight;
      cursor: not-allowed;
    }
  }

  #log {
    ul {
      list-style: none;
      margin: 0;
      padding: 0;
    }

    li {
      margin: 0.5rem 0;
    }
  }


  .log {
    &--player {
        color: #7700ff;
    }

    &--monster {
        color: #da8d00;
    }

    &--damage {
        color: red;
    }

    &--heal {
        color: green;
    }
  }

</style>