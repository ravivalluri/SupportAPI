<template>
  <div class="info">
    <div class="routes">
      <h1>Supporter App API</h1>
      <h2>Available Routes</h2>
      <p v-for="route in routes" :key="route.route" @click="setActive(route)">{{ route.route }}</p>
    </div>
    <div class="resp">
      <textarea name="return" rows="20" cols="80" v-model="returnVal"></textarea>
    </div>
  </div>
</template>

<script>
const returnBase = `['willis', 'john_hancock', 'aon', 'thompson', 'bcbs']`;
const returnBuildings = `[
  ...
  {
    building: "Thompson",
    roomNumber: 1001,
    hasHDMI: false,
    hasVGA: true
  },
  {
    building: "Thompson",
    roomNumber: 1000,
    hasHDMI: false,
    hasVGA: true
  },
  {
    building: "Thompson",
    roomNumber: "Printer",
    hasHDMI: false,
    hasVGA: true
  },
  ...
]`;

const returnRoom = `[
  {
    building: "Thompson",
    roomNumber: 1001,
    hasHDMI: false,
    hasVGA: true
  },
]`;

const returnDevices = `[
  ...
  {
    _id: "macbook-air-2015-2017",
    name: "Macbook Air 2015-2017",
    hasHDMI: false,
    hasVGA: false,
    adapterHDMI: "Thunderbolt-HDMI",
    adapterVGA: "Thunderbolt-VGA",
    linkHDMI:
      "https://www.amazon.com/s?k=thunderbolt+to+HDMI+adapter&ref=nb_sb_noss_2",
    linkVGA:
      "https://www.amazon.com/s?k=thunderbolt+to+vga+adapter&ref=nb_sb_noss_2"
  },
  {
    _id: "macbook-pro-2017-2019",
    name: "Macbook/Macbook Pro 2017-2019",
    hasHDMI: true,
    hasVGA: false,
    adapterHDMI: "Thunderbolt-HDMI",
    adapterVGA: "Thunderbolt-VGA",
    linkHDMI:
      "https://www.amazon.com/s?k=thunderbolt+to+HDMI+adapter&ref=nb_sb_noss_2",
    linkVGA:
      "https://www.amazon.com/s?k=thunderbolt+to+vga+adapter&ref=nb_sb_noss_2"
  },
  ...
]`;

const returnDevice = `[
 {
    _id: "macbook-pro-2017-2019",
    name: "Macbook/Macbook Pro 2017-2019",
    hasHDMI: true,
    hasVGA: false,
    adapterHDMI: "Thunderbolt-HDMI",
    adapterVGA: "Thunderbolt-VGA",
    linkHDMI:
      "https://www.amazon.com/s?k=thunderbolt+to+HDMI+adapter&ref=nb_sb_noss_2",
    linkVGA:
      "https://www.amazon.com/s?k=thunderbolt+to+vga+adapter&ref=nb_sb_noss_2"
  },
]`;

export default {
  name: "App",
  data() {
    return {
      routes: [
        { route: "/", return: "The server redirects to this endpoint." },
        { route: "/buildings", return: returnBase },
        { route: "/buildings/:building", return: returnBuildings },
        { route: "/buildings/:building/:room", return: returnRoom },
        { route: "/devices", return: returnDevices },
        { route: "/devices/:device", return: returnDevice }
      ],
      activeRoute: "",
      returnVal: ""
    };
  },
  methods: {
    setActive(route) {
      this.activeRoute = route.route;
      this.returnVal = route.return;
    }
  }
};
</script>

<style scoped>
h1 {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
h2 {
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
}
a {
  color: #00b7ff;
  text-decoration: none;
}
textarea {
  height: 60vh;
  border-radius: 10px;
  outline: none;
  background-color: #2b3a42;
  color: #eff2e2;
  padding: 1vw;
  font-family: monospace;
  font-size: 1em;
}
p {
  font-family: monospace;
  border: 1px solid grey;
  border-radius: 5px;
  padding: 0.5vw;
  background-color: #2b3a42;
  color: #eff2e2;
}
p:hover {
  box-shadow: 2px 5px 3px 0px #ccc;
  cursor: pointer;
}
p:active {
  box-shadow: 1px 2px 0px 0px #ccc;
  cursor: pointer;
}
.info {
  display: flex;
  justify-content: space-around;
}
.routes {
  margin-left: 3vw;
  max-width: 20vw;
}
.resp {
  width: 50vw;
  margin-top: 12vh;
}
</style>
