<template lang="html">
  <div id="exemplo">
      <table class="table">
        <thead>
          <th><a href="#" @click="sort($event, 'fields.titulo')">Titulo</a></th>
          <th><a href="#" @click="sort($event, 'fields.plataformas')">Plataformas</a></th>
        </thead>
        <tbody>
            <tr v-for="game in lista">
              <td>{{ game.fields.titulo }}</td>
              <td>{{ game.fields.plataformas }}</td>
            </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
  export default {

    data() {
      return {
        sortDirection: 'desc',
        lista: []
      }
    },
    mounted() {
      this.$http.get("homepage/games")
                .then( (resp) => this.lista = resp.data)
    },
    methods: {
      sort(event, campo) {
        event.preventDefault()
        this.sortDirection = this.sortDirection == "desc" ? "asc" : "desc"
        this.lista = _.orderBy(this.lista, campo, this.sortDirection)
      }
    }
  }
</script>

<style lang="css">
  #exemplo {
    color: red;
  }
</style>
