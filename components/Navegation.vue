<template>
  <div class="navegation">
    <img class="navegation__logo" src="@/assets/images/logoo.png" alt="logo" />
    <div class="navegation__itmes-wrapper">
      <input placeholder="Search" type="text" />
      <ul>
        <span>About</span>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navegation",
};
</script>

<style lang="css" scoped>
.navegation {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 10rem;
  background-color: #4da0db;
  margin-bottom: 2rem;
}

.navegation__logo {
  width: 200px;
}

.navegation__itmes-wrapper {
  display: flex;
  align-items: center;
}

.navegation__itmes-wrapper input {
  border-radius: 25px;
  border: 2px solid #6fe153;
  outline: none;
  padding-left: 1rem;
  height: 50px;
}

.navegation__itmes-wrapper ul {
  list-style: none;
  display: block;
  margin: 0;
  font-size: 20px;
}

.navegation__itmes-wrapper ul:hover {
  color: #6fe153;
}
</style>
