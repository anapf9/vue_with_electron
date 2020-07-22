<template>
  <v-container fluid>
    <v-form>
      <v-file-input
        label="Selecione as legendas"
        append-icon="mdi-send"
        prepend-icon="mdi-message-text"
        mutiple
        chips
        outlined
        v-model="files"
        @click:append="processSubtitle"
      />
    </v-form>
    <div class="pills">
      <Pill
        v-for="word in grouppedWords"
        :key="word.name"
        :name="word.name"
        :amount="word.amount"
      />
    </div>
  </v-container>
</template>

<script>
import Pill from "@/components/Pill.vue";
export default {
  name: "HelloWorld",
  components: {
    Pill,
  },
  data: () => ({
    files: "",
    grouppedWords: [
      { name: "you", amount: 900 },
      { name: "he", amount: 853 },
      { name: "why", amount: 1745 },
    ],
  }),
  methods: {
    processSubtitle() {
      console.log("subtitle", this.files);
    },
  },
};
</script>
<style lang="css" scoped>
.pills {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>
