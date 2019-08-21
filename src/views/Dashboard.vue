<template>
  <div class="home">
    <FlashCard
      subject="Animals"
      question="Which animal goes 'woof'?"
      answer="Doggos!"
      hint="Often called Fido"
    />
  </div>
</template>

<script>
import FlashCard from "../components/FlashCard/FlashCard";

export default {
  name: "dashboard",
  components: {
    FlashCard
  }
};
</script>
