<template>
  <header>
    <div>
      <h1>Hey</h1>
      <div class="grid grid-cols-6 border-solid ">
        <div class="bg-green-200 col-start-2 col-span-4 border-4 border-black">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi deleniti dolorem eius et excepturi itaque necessitatibus qui quisquam repellendus rerum? Explicabo numquam perferendis quas. Consequuntur dolorem expedita magnam minima suscipit.
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deleniti doloribus earum odio pariatur voluptates! Aliquid aperiam culpa esse expedita, explicabo itaque minus nesciunt, non provident quam soluta tenetur, vero? Similique.
          {{ API_KEY }}
          </p>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import axios from "axios";

export default {
  name: "Profile",
  data() {
    return {
      STEAM_ID: 76561198090558573,
      API_KEY: process.env.VUE_APP_API_KEY
      }
    },
  async created(){
    try {
      let result = await axios.get(`http://localhost/test_realiz3D_laravel/public/api/groupTypes`);
      this.groupTypes = result.data.reverse();
    } catch (e) {
      console.error(e);
    }
  }
};
</script>

<style>

</style>