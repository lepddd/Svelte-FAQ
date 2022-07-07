<script>
  import Question from "./components/Question.svelte";

  const gradientColors = [
    { color1: "#3F37C9", color2: "#4CC9F0" },
    { color1: "#EC008C", color2: "#FC6767" },
    { color1: "#FFA751", color2: "#FFE259" },
    { color1: "#654EA3", color2: "#EAAFC8" },
  ];

  const list = [
    {
      question: "How do i apply?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus iaculis finibus tortor, id lobortis ligula ornare in. Sed interdum nunc quis risus tempor dictum. Pellentesque eu cursus nunc.",
    },
    {
      question: "Lost or forgotten your password?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus iaculis finibus tortor, id lobortis ligula ornare in. Sed interdum nunc quis risus tempor dictum. Pellentesque eu cursus nunc.",
    },
    {
      question: "How can i make a change to my application?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus iaculis finibus tortor, id lobortis ligula ornare in. Sed interdum nunc quis risus tempor dictum. Pellentesque eu cursus nunc.",
    },
    {
      question: "How can i update my name?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus iaculis finibus tortor, id lobortis ligula ornare in. Sed interdum nunc quis risus tempor dictum. Pellentesque eu cursus nunc.",
    },
  ];

  let currentActive = 0;
</script>

{#each list as item, index}
  <Question
    {item}
    --color1={gradientColors[index].color1}
    --color2={gradientColors[index].color2}
    {index}
    on:select={(e) => (currentActive = e.detail)}
    current={currentActive}
  />
{/each}
