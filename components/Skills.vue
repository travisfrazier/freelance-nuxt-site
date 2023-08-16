<template>
    <section class="skills__section">
      <div class="skill__item">
        <h2>Squarespace</h2>
        <p>5 Years Experience</p>
      </div>
      <div class="skill__item">
        <h2>Shopify</h2>
        <p>4.5 Years Experience</p>
      </div>
      <div class="skill__item">
        <h2>Headless Sites</h2>
        <p>3 Years Experience</p>
      </div>
      <div class="skill__item">
        <h2>Wordpress</h2>
        <p>1 Years Experience</p>
      </div>
      <div class="skill__item">
        <h2>Freelance</h2>
        <p>7 Years Experience</p>
      </div>
    </section>
  </template>
  
  <script>
  </script>
  
  <style lang="scss" scoped>
  .skills__section {
    overflow-x: hidden;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    padding: 50px 0px 80px 0px;
    grid-row-gap: 60px;
    @media only screen and (max-width: $tablet) {
        grid-template-columns: 1fr 1fr;
    }
    @media only screen and (max-width: $mobile) {
        grid-template-columns: 1fr;
        justify-items: center;
        text-align: center;
    }
  }
  
  h2 {
    @include font-l;
  }
  </style>