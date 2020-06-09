<template>
  <carousel :slides="items" />
</template>

<script>
import Carousel from "@/components/Carousel/Carousel";

export default {
  name: "App",
  components: {
    Carousel
  },
  data() {
    return {
      items: [
        {
          image: require("@/assets/images/img-1.jpg"),
          title: "What is Lorem Ipsum?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."
        },
        {
          image: require("@/assets/images/img-2.jpg"),
          title: "Why do we use it?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."
        },
        {
          image: require("@/assets/images/img-3.jpg"),
          title: "Where does it come from?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."
        },
        {
          image: require("@/assets/images/img-4.jpg"),
          title: "Where can I get some?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old."
        }
      ]
    };
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: "Open Sans", sans-serif;
}
</style>
