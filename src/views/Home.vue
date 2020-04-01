<template>
  <div class="container">
    <div class="row">
       <div class="col-md-2"></div>
       <div class="col-md-8">
         <h4>Simple Short Url</h4>
            <form v-on:submit.prevent="addLink" class="my-4 form-inline mt-3">
                <label for="fullUrl" class="sr-only">Full Url</label>
                <input v-model="link" required placeholder="Masukkan Url" type="text" class="form-control col mr-2" id="link">
            <button type="submit" class="btn btn-primary">Pendekkan Url</button>
            </form>
            <h4>{{url}}</h4>
            <router-link to="/login">Login</router-link> |
            <router-link to="/login">Register</router-link>
       </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Short',
  data () {
    return {
      title: '',
      url: '',
      link: ''
    }
  },
  methods: {
    async addLink () {
      try {
        const response = await axios.post('http://localhost:5000/short_url', {
          title: this.link,
          url: this.link
        })
        const hasil = response.data.data.short_url
        this.url = `http://localhost:5000/short_url/${hasil}`
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
