<template>
  <v-app>
      <v-card class="overflow-hidden no-radius">
        <v-app-bar
          absolute
          id="main-nav-bar"
        >
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
          <v-app-bar-title>taylorglenn.games</v-app-bar-title>
          <v-spacer></v-spacer>
          <template v-slot:extension>
            <v-tabs align-with-title>
              <v-tab id="about-tab">about</v-tab>
              <v-tab id="games-tab">games</v-tab>
              <v-tab id="collection-tab">collection</v-tab>
            </v-tabs>
          </template>
        </v-app-bar>
        <v-sheet max-height="100vh" >
          <v-container style="height: 100vh;">
            <v-main id="main-content">

            </v-main>
          </v-container>
        </v-sheet>
      </v-card>
  </v-app>
</template>

<script lang="ts">

import { defineComponent } from 'vue'

export default defineComponent({
    name: "App",
    data() {
        return {
        //
        };
    },
    components: {  }
})
</script>

<style>
:root {
  --neon-pink: #ff10f0;
  --neon-red: #ff3131;
  --neon-orange: #ff5f1f;
  --neon-yellow: #ffff00 ;
  --neon-green: #39ff14;
  --neon-blue: #1f51ff;
  --neon-indigo: #6f00ff;
  --neon-violet: #9d00ff;

  --darker-than-midnight: #20292d;
  --midnight: #242e33;
  --soft-white: #fbfaf5; 

  --tab-slider-height-hover-px: 3px;
  --tab-slider-height-active-px: 6px;
}

.v-sheet {
  background-color: var(--midnight) !important; /* this feels like bad css but i'm tired of fucking with it */
}

.no-radius {
  border-radius: 0;
}

#main-nav-bar {
  color: var(--soft-white);
  background-image: url(./assets/blue-universe-small.jpg);
}

#main-nav-bar:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background-image: linear-gradient(45deg, var(--darker-than-midnight) 50%, rgba(0,0,0,0));
}

.v-tab .v-tab__slider {
  box-sizing: border-box;
  height: var(--tab-slider-height-active-px);
  backdrop-filter: blur();
}

.v-tab:hover.v-tab:not(.v-tab--selected) .v-tab__slider {
  animation: fadeIn .5s;
  box-sizing: border-box;
  opacity: 1;
  height: var(--tab-slider-height-hover-px);
  background: currentColor;
}

.v-tab--selected .v-tab__slider {
  animation: tabSliderGrowUp .4s;
}

#about-tab .v-tab__slider {
  background: linear-gradient(90deg, var(--neon-pink) 0%, var(--neon-red) 100%);
}

#games-tab .v-tab__slider {
  background: linear-gradient(90deg, var(--neon-orange) 0%, var(--neon-yellow) 100%);
}

#collection-tab .v-tab__slider {
  background: linear-gradient(90deg, var(--neon-green) 0%, var(--neon-blue) 100%);
}

@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

@keyframes tabSliderGrowUp {
  0% { height: var(--tab-slider-height-hover-px); }
  100% { height: var(--tab-slider-height-active-px); }
}

</style>
