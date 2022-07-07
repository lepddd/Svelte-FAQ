<script>
  import { createEventDispatcher, onDestroy, onMount } from "svelte";

  const dispatch = createEventDispatcher();

  export let item;
  export let index;
  export let current;

</script>

<div class="question-container" class:active={current == index}>
  <div class="title" on:click={() => dispatch("select", index)}>
    <p class="question-index" class:active={current == index}>
      {index > 9 ? "" : "0"}{index + 1}
    </p>
    <span class="question-title" class:active={current == index}
      >{item.question}</span
    >
    <span class="question-icon" class:active={current == index}>+</span>
  </div>
  <div class="body">{item.answer}</div>
</div>

<style>
  .question-container {
    min-width: 320px;
    max-width: 900px;
    width: 100%;
    height: 60px;
    overflow: hidden;
    padding: 10px 20px;
    margin: 10px 0;
    border-radius: 10px;
    box-shadow: 0px 10px 10px -5px rgba(0, 0, 0, 0.04),
      0px 20px 25px -5px rgba(0, 0, 0, 0.1);
    transition: height 0.5s ease-in-out;
  }
  .title {
    position: relative;
    display: flex;
    align-items: center;
    cursor: pointer;
  }
  .question-index {
    width: 40px;
    height: 40px;
    text-align: center;
    line-height: 40px;
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    border-radius: 10px;
    transition: .5s ease-in-out;
  }
  .question-title {
    font-size: 16px;
    width: calc(100% - 80px);
    margin-left: 10px;
    font-weight: 700;
  }
  .question-title.active {
    padding: 15px;
    width: calc(100% - 50px);
    margin-left: 0px;
    background-color: #fff;
  }
  .question-icon {
    position: absolute;
    right: 0px;
    font-size: 16px;
    font-weight: 700;
  }
  .question-icon.active {
    transform: rotateZ(45deg);
    color: #fff;
    right: 10px;
  }
  .body {
    margin-top: 10px;
    font-size: 16px;
    color: #fff;
    font-weight: 500;
  }

  .question-container.active {
    padding: 10px;
    height: 250px;
    background: linear-gradient(94.41deg, var(--color1) 0%, var(--color2) 100%);
  }
  .question-index {
    background: linear-gradient(135deg, var(--color1) 0%, var(--color2) 100%);
  }
  .question-index.active {
    position: absolute;
    font-size: 128px;
    background: initial;
    color: rgba(255, 255, 255, 0.2);
    width: 100%;
    height: 230px;
    top: 0;
    right: 0px;
    line-height: 230px;
  }
  @media screen and (min-width: 768px) {
    .question-container {
      height: 80px; 
      margin: 16px 0;
    }
    .question-index {
      width: 60px;
      height: 60px;
      line-height: 60px;
      font-size: 32px;
    }
    .question-title {
      font-size: 24px;
      width: calc(100% - 80px);
      margin-left: 20px;
    }
    .question-title.active {
      padding: 10px;
      width: initial;
    }
    .question-icon {
      font-size: 24px;
    }
    .question-icon.active {
      right: 0;
    }
    .body {
      margin-top: 20px;
      font-size: 20px;
    }
    .question-container.active {
      padding: 20px;
    }
    .question-index.active {
      font-size: 128px;
      width: initial;
      right: 10px;
      height: 230px;
      line-height: 230px;
    }
  }
  @media screen and (min-width: 1024px) {
    .question-title {
      font-size: 32px;
    }
    .question-icon {
      font-size: 32px;
    }
    .body {
      font-size: 24px;
    }
  }
</style>
