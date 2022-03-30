<script>
  export default {
    data() {
      return {
        image: "./src/assets/dog2.jpeg",
        checkedNames: [],
        show: true
      }
    },
    methods: {
      changeImage: function() {
        if(this.image == "./src/assets/dog1.jpeg"){
          this.image = "./src/assets/dog2.jpeg"
        } else{
          this.image = "./src/assets/dog1.jpeg"
        }
      }
    }
  }
</script>

<template>
  <div id="example">
    <h1 class="green">Human's best friend</h1>
    <img alt="dog" class="logo" :src="image" width="450" height="300" />
    <button @click="changeImage">See more images</button>
    <div class="cardsSection">
      <div class="card" style="width: 18rem;">
        <div class="card-body">
          <h5 class="card-title"><a href="https://rescuedpetsmovement.org/">Rescued Pets Movement</a></h5>
          <p class="card-text">Get to know more about the actions of Rescued Pets Movement.</p>
        </div> 
      </div>
      <div class="card" style="width: 18rem;">
        <div class="card-body">
          <h5 class="card-title"><a href="https://rolda.org/?gclid=Cj0KCQjw3IqSBhCoARIsAMBkTb1QdKP9iIIX7qFiyQnx3RIoNyZL2ZJP0BfF5nM_pukaCWWj3bTkmXEaAv1qEALw_wcB">ROLDA</a></h5>
          <p class="card-text">Get to know more about the actions of ROLDA.</p>
        </div> 
      </div>
    </div>
  </div>
  
  <div id="bindingExample">
    <h2>Favorite pets</h2>
    <p>Select your favorite pets from the list below.</p>
   
    <input type="checkbox" id="turtle" value="Turtle" v-model="checkedNames">
    <label for="turtle">Turtle</label>
    <input type="checkbox" id="cat" value="Cat" v-model="checkedNames">
    <label for="cat">Cat</label>
    <input type="checkbox" id="fish" value="Fish" v-model="checkedNames">
    <label for="fish">Fish</label>
    <button @click="show = !show">Toggle List</button>
  </div>

  <div id="LoopArrayExample">
    <ul v-if="show && checkedNames.length">
      <li v-for="animal of checkedNames">{{ animal }}</li>
    </ul>
    <p v-else-if="checkedNames.length">The list is hidden.</p>
    <p v-else>The list is empty.</p>
  </div>

  <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-indicators">
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item active">
      <img src="./assets/turtle.jpeg" class="d-block w-100" alt="turtle">
    </div>
    <div class="carousel-item">
      <img src="./assets/cat.jpeg" class="d-block w-100" alt="cat">
    </div>
    <div class="carousel-item">
      <img src="./assets/fish.jpeg" class="d-block w-100" alt="fish">
    </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
  <br>
</template>

<style>
  @import './assets/base.css';

  #app {
    max-width: 1280px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  #example{
    display: grid;
    margin: 0 auto;
    padding: 2rem;
    justify-content: space-evenly;
  }

  h1 {
    font-weight: 500;
    font-size: 2.6rem;
    top: -10px;
    display: flex;
    text-align: center;
  }

  .logo {
    display: flex;
    margin: 0 auto 2rem;
    padding-bottom: 20px;
  }

  a,
  .green {
    text-decoration: none;
    color: hsla(160, 100%, 37%, 1);
    transition: 0.4s;
  }

  button {
    background-color: hsla(160, 100%, 37%, 1);
    color: white;
    padding: 10px;
    font-size: 20px;
    border: 0px;
    margin: 0 auto 2rem;
  }

  #bindingExample {
    display: inline;
    align-content:space-between;
    padding: 10px;
  }

  #bindingExample label {
    padding-right: 25px;
  }

  #LoopArrayExample {
    display: inline;
    padding: 10px;
  }

  #example .cardsSection {
    display: flex;
    align-content: space-between;
  }

  #carouselExampleIndicators {
    margin: 0 auto;
    padding: 2rem;
  }
</style>
