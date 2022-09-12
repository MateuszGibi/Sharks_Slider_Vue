<script>

import Menu from "./components/Menu.vue";
import Slider from "./components/Slider.vue";

export default {

  components: {
    Menu,
    Slider
  },

  data() {

    return {
      data: [
        {
          Image: "./images/1.jpg",
          Title: "Quisque vulputate mi consectetur",
          SubTitle: "Quisque vulputate mi consectetur",
          Content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed posuere quis mi a fermentum. Nulla vel fringilla quam. Quisque a nulla euismod, finibus est eu, molestie lectus. Nam rhoncus nec nibh sit amet rhoncus. Donec mauris dolor, suscipit a felis auctor, dignissim imperdiet mi. Nulla facilisi. Praesent lobortis in purus in bibendum. Pellentesque eleifend, dui sit amet scelerisque hendrerit, mauris diam fermentum massa, et posuere nisl orci sed mi. In leo libero, sollicitudin eu felis in, egestas ultrices dui. Integer sed libero egestas, faucibus lectus ac, consectetur enim.",
          Btn1Val: "LOREM IPSUM",
          Btn2Val: "DOLOR SIT AMET",
        },
        {
          Image: "./images/2.jpg",
          Title: "Pellentesque eleifend, dui sit amet",
          SubTitle: "Mauris diam fermentum massa.",
          Content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed posuere quis mi a fermentum. Nulla vel fringilla quam. Quisque a nulla euismod, finibus est eu, molestie lectus. Nam rhoncus nec nibh sit amet rhoncus. Donec mauris dolor, suscipit a felis auctor, dignissim imperdiet mi. Nulla facilisi. Praesent lobortis in purus in bibendum. Pellentesque eleifend, dui sit amet scelerisque hendrerit, mauris diam fermentum massa, et posuere nisl orci sed mi. In leo libero, sollicitudin eu felis in, egestas ultrices dui. Integer sed libero egestas, faucibus lectus ac, consectetur enim.",
          Btn1Val: "LOREM IPSUM",
          Btn2Val: "DOLOR SIT AMET",
        },
        {
          Image: "./images/3.jpg",
          Title: "Nam rhoncus nec nibh sit amet",
          SubTitle: "Donec mauris dolor, suscipit a felis auctor.",
          Content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed posuere quis mi a fermentum. Nulla vel fringilla quam. Quisque a nulla euismod, finibus est eu, molestie lectus. Nam rhoncus nec nibh sit amet rhoncus. Donec mauris dolor, suscipit a felis auctor, dignissim imperdiet mi. Nulla facilisi. Praesent lobortis in purus in bibendum. Pellentesque eleifend, dui sit amet scelerisque hendrerit, mauris diam fermentum massa, et posuere nisl orci sed mi. In leo libero, sollicitudin eu felis in, egestas ultrices dui. Integer sed libero egestas, faucibus lectus ac, consectetur enim.",
          Btn1Val: "LOREM IPSUM",
          Btn2Val: "DOLOR SIT AMET",
        }
      ]
    }
  }
}

</script>

<template>

  <Menu />
  <Slider :sliderData='this.data' />

</template>

