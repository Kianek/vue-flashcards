<template>
  <v-card class="flash-card">
    <div class="content">
      <h2 class="mt-2 text-center">{{ subject }}</h2>
      <div class="front" v-if="!flipped">
        <v-card-text>{{ question }}</v-card-text>
        <v-card-text v-if="showHint">Hint: {{ hint }}</v-card-text>
      </div>
      <div class="back" v-else>
        <v-card-text>{{ answer }}</v-card-text>
      </div>

      <v-card-actions class="btn-group">
        <v-btn
          class="mb-2"
          block
          color="primary"
          depressed
          @click="showHint = !showHint"
          v-if="!flipped && hint"
        >hint?</v-btn>
        <v-btn class="ml-0" block depressed @click="flipped = !flipped">flip</v-btn>
      </v-card-actions>
    </div>
  </v-card>
</template>

<script>
export default {
  props: {
    subject: String,
    question: String,
    answer: String,
    hint: String
  },
  data() {
    return {
      flipped: false,
      showHint: false
    };
  }
};
</script>

<style lang="scss" scoped>
.flash-card {
  height: 250px;
  width: 350px;
  perspective: 1000px;
}

.content {
  display: flex;
  flex-direction: column;
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
}

.front,
.back {
  width: 100%;
}

.btn-group {
  margin-top: auto;
  padding: 0.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>