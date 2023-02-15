<template>
  <div>
  <div v-for="d in dat.SampleModel" :key=d.title align="center">
          <h2>
            ID:{{d.id}} <br>
            title:{{d.title}} <br>    
             comment:{{d.description}} 
          </h2>
        </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dat: []
    }
  },
  async mounted(){
    const url = "/get_person/" 
    const response = await this.$axios.get(url)
    this.dat = response.data
  }
}
</script>
