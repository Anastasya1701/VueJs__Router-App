<template>
  <div>
    <h3>Edit the User</h3>
    <div>User loaded has ID : {{ $route.params.id}}</div>
    <div>route.query.local: {{$route.query.local}}</div>
    <div>route.query.q: {{$route.query.q}}</div>
    <hr>
    <button class="btn btn-primary">Confirm</button>
    <div :style="{height: 500 + 'px'}"></div>
    <div id="anchor-data">Context anchor data</div>
    <hr>
    <button @click="leavePage = true" class="btn btn-primary">Leave Page</button>
    <hr>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        leavePage: false
      }
    },
    beforeRouteLeave(to, from, next) {
      if (this.leavePage) {
        confirm('Do you want to leave Page?') ?
          next() : next(false)
      }
    }
  }
</script>
