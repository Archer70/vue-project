<template>
    <div class="message">
        <div class="likes">
            <a class="like-link" @click.prevent="likePost">Like</a>
            {{ likes }}
        </div>
        {{ messageText }}
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
