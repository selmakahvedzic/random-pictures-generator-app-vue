<template>
  <div>
    <b-col>
      <b-card
        title="Dog card"
        :img-src="dog"
        img-alt="Image"
        img-top
        img-height="200px"
        tag="article"
        style="max-width: 20rem"
        class="dog-card"
        id="image-card"
      >
        <b-card-text> This is the Dog Card I made for this task. </b-card-text>
      </b-card>
    </b-col>
  </div>
</template>

<script>
export default {
  props: {
    dog: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped></style>
