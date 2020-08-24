<template>
  <div class="page">
    <div class="loadings">
      <Loading name="plane" color="green" />
      <Loading name="chase" color="pink" />
      <Loading name="bounce" color="red" />
      <Loading name="wave" color="grey" />
      <Loading name="pulse" color="orange" />
      <Loading name="flow" color="blue" :nums="4" />
      <Loading name="swing" color="blue" />
      <Loading name="circle" />
      <Loading name="circle-fade" />
      <Loading name="grid" />
      <Loading name="fold" />
      <Loading name="wander" />
    </div>

    <div ref="content" class="content">
      <!-- v-loading="loading"
      :loading-name="loadingName"
      :loading-color="loadingColor" -->
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti ad ullam
      voluptatem reiciendis voluptas eveniet optio tenetur eum voluptatum quam,
      reprehenderit pariatur dolorem iure quos molestias esse quo, laudantium
      vitae!
    </div>
    <button @click="showLoader">Show Loading</button>
    <button @click="hideLoader">Hide Loading</button>
    <button @click="changeStyle">Change Style</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading: true,
      loadingName: 'flow',
      loadingColor: 'red',
      loader: null,
    }
  },
  methods: {
    showLoader() {
      this.loader = this.loader || this.$loading({ el: this.$refs.content })
      this.loader.show()
    },
    hideLoader() {
      this.loader.hide()
    },
    changeStyle() {
      const names = ['plane', 'chase', 'bounce', 'wave', 'pulse', 'flow']
      const colors = ['blue', 'red', 'yellow']
      this.loadingName = names[Math.floor(Math.random() * names.length)]
      this.loadingColor = colors[Math.floor(Math.random() * colors.length)]
    },
  },
}
</script>

<style>
.page {
  height: 100vh;
  width: 100vw;
  padding: 0 20%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.loadings {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
}

.content {
  margin-top: 12px;
  width: 100%;
  height: 200px;
  background-color: rgb(206, 206, 206);
}
</style>
