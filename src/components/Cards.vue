<template>
  <b-container>
    <div v-if="meals.length">
      <b-row>
        <b-col v-for="(meal, index) in meals" :key="index">
          <b-card
            :title="meal.strCategory"
            :img-src="meal.strCategoryThumb"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem"
            class="mb-2"
          >
            <b-card-text>{{ mealDescriptionFormatted(meal) }}</b-card-text>

            <b-button href="#" variant="info">View food</b-button>
          </b-card>
        </b-col>
      </b-row>
    </div>

    <div v-else>
      <em>No meals available yet</em>
      😢
    </div>
  </b-container>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      meals: []
    }
  },
  mounted() {
    const url = 'https://www.themealdb.com/api/json/v1/1/categories.php'
    axios
      .get(url)
      .then(response => {
        this.meals = response.data.categories
      })
      .catch(err => {
        console.log(err)
      })
  },
  methods: {
    mealDescriptionFormatted(meal) {
      return `${meal.strCategoryDescription.slice(0, 100).trim()}…`
    }
  }
}
</script>
