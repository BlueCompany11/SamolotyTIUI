<template>
    <div class="home">
        <label v-text="listaSamolotowPasazerskich"></label>
        <label v-text="modelsamolotou1"></label>
    </div>
</template>

<script>// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'Main',
  data: function(){
    return {
        listaSamolotowPasazerskich: [],
        modelsamolotou1: "",
    }
  },
  mounted(){
    axios
      .get('http://localhost:58177/api/SamolotPasazerski')
        .then(response => {
            this.listaSamolotowPasazerskich = response.data
            this.modelsamolotou1 = response.data[0]["model"]
        })
  },
}</script>
