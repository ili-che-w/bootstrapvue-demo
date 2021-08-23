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
            <b-card-text>{{
              `${meal.strCategoryDescription.slice(0, 100).trim()}…`
            }}</b-card-text>
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
export default {
  data() {
    return {
      meals: [
        {
          idCategory: 1,
          strCategory: 'cookies',
          strCategoryDescription:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi error, quibusdam exercitationem cumque culpa atque ex! Inventore at maiores, alias officiis, ducimus nemo sequi laborum voluptate nulla impedit quas ullam? Fugit modi ut aliquam provident suscipit.'
        },
        {
          idCategory: 2,
          strCategory: 'french fries',
          strCategoryDescription:
            'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Consequuntur, labore dignissimos rem sint est aut deleniti, corporis laborum quam sit odio alias vel commodi laudantium enim dolorum deserunt velit cupiditate, provident repudiandae porro corrupti qui repellat facilis. Quasi, vel.'
        }
      ]
    }
  }
}
</script>
