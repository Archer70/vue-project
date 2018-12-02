<template>
    <div class="message">
        <span class="likes">
            <a class="like-link" @click.prevent="likePost">Like</a>
            {{ likes }}
        </span>
        <span>{{ messageText }}</span>
    </div>
</template>

<script>
export default {
  name: 'Message',
  props: {
    messageText: String
  },
  data() {
      return {
          likes: 0,
      }
  },
  methods: {
      likePost() {
          this.likes++;
      }
  }
}
</script>

<style scoped>
.message {
    padding: 1rem;
    border-bottom: 1px solid #efefef;
}

.like-link {
    cursor: pointer;
    color: blue;
}
</style>
