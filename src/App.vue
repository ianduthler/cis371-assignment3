<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="b in bases" :key="b.id">
          <label>
            <input
              type="radio"
              name="base"
              :id="`r${b.id}`"
              :value="b"
              v-model="currentBase"
            />
            {{ b.name }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="c in creamers" :key="c.id">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${c.id}`"
              :value="c"
              v-model="currentCreamer"
            />
            {{ c.name }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="s in syrups" :key="s.id">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${s.id}`"
              :value="s"
              v-model="currentSyrup"
            />
            {{ s.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import {
  temps,
  bases,
  creamers,
  syrups,
  currentTemp,
  currentBase,
  currentCreamer,
  currentSyrup,
} from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
