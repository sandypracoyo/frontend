<template>
  <div class="container">
    <div class="row">
       <div class="col-md-2"></div>
       <div class="col-md-8">
            <form v-on:submit.prevent="addLink" class="my-4 form-inline">
                <label for="fullUrl" class="sr-only">Full Url</label>
                <input required placeholder="Masukkan Url" type="url" class="form-control col mr-2" name="link" id="link">
            <button type="submit" class="btn btn-primary">Pendekkan Url</button>
            </form>
            <h4>Short Link : http://localhost:3000/sds123</h4>
       </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
const url = 'http://localhost:5000'
export default {
  name: 'Short',
  data () {
    return {
      title: '',
      url: ''
    }
  },
  methods: {
    async addLink () {
      try {
          const add = await axios.post()
      } catch (error) {
          
      }
    }
  }
}
</script>
