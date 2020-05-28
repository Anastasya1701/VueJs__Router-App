<template>
  <div>
    <hr>
    <div>User Detail</div>
    <h3>Edit the User</h3>
    <div>User loaded has ID : {{ $route.params.id}}</div>
    <hr>
    <router-link :to="link" tag="button" class="btn btn-primary">
      Edit User
    </router-link>
    <hr>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        link: {
          name: 'userEdit',
          params: {
            id: this.$route.params.id
          },
          query: {
            local: 'en', q: 100
          },
          hash: '#anchor-data'
        },
        beforeRouteEnter(to, from, next) {
          // this.link - will not work, as component haven`t been created
          next(vm => {
            console.log(vm.link)
          })
        }
      }
    }
  }
</script>
