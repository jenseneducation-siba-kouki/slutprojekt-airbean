<template>
  <div class="menuitem">
    
    <div class="add">
      <button @click="add">
        <img src="../assets/graphics/add.svg" alt="add" />
      </button>
    </div>
    <h3 class="itemtitle">
      {{ item.title }}
      <div class="dotted-line"></div>
    </h3>
    <p class="itemdesc">{{ item.desc }}</p>
    <h3 class="itemprice">{{ item.price}} kr</h3>
  </div>
</template>

<script>
export default {
  name: "Menuitem",
  props: {
    item: Object
  },
  methods: {
    add() {
      this.$store.dispatch("addToCart", this.item);
    }
  }
};
</script>
//  this.$store.dispatch.additemTocart, { item: this.item, quantity: 1 };

<style lang ="scss">
.menuitem {
  display: grid;
  grid-template-rows: 1.5 rem 1.5 rem;
  grid-template-columns: 3rem 1fr 4rem;
  margin: 2rem 0 2rem 0;

  .add {
    display: flex;
    grid-column: 1/2;
    grid-row: 1/2;
    margin-top: -33px;

    button {
      background: black;
      border-radius: 100%;
      align-items: center;
      justify-content: center;
      margin-left: 10px;
      display: flex;
      height: 1.5rem;
      width: 1.5rem;
      margin-top:50px;
    }
    img {
      width: 15px;
    }
  }

  .itemtitle {
    grid-column: 2/3;
    grid-row: 1/2;
    font-size: 1.3rem;
    display: flex;
    margin: 0;
    padding: 0;

    .dotted-line {
      display: flex;
      margin-bottom: 25px;
      flex: 1;
      border-bottom: 2px dotted rgb(189, 171, 171);
    }
  }
  .itemdesc {
    display: flex;

    /* position: relative; */
    font-size: 15px;
    grid-row: 2/3;
    grid-column: 2/3;
    padding: 0px;

    margin: 0;
  }
  .itemprice {
    display: flex;
    font-size: 25px;
    grid-row: 1/2;
    grid-column: 3/4;
    padding: 0;
    margin: 0;
    font-weight: bold;
  }
}
</style>