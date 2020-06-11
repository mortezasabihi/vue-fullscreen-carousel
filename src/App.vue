<template>
  <carousel :slides="items" />
</template>

<script>
import Carousel from "@/components/Carousel/Carousel";

export default {
  name: "App",
  components: {
    Carousel,
  },
  data() {
    return {
      items: [
        {
          image:
            "https://images.wallpaperscraft.com/image/stones_rocks_sea_173013_3840x2400.jpg",
          title: "What is Lorem Ipsum?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.",
        },
        {
          image:
            "https://images.wallpaperscraft.com/image/stones_rocks_coast_172090_3840x2400.jpg",
          title: "Why do we use it?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.",
        },
        {
          image:
            "https://images.wallpaperscraft.com/image/stones_waves_blocks_164110_3840x2400.jpg",
          title: "Where does it come from?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.",
        },
        {
          image:
            "https://images.wallpaperscraft.com/image/stones_waves_rocks_165899_3840x2400.jpg",
          title: "Where can I get some?",
          description:
            "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.",
        },
      ],
    };
  },
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
