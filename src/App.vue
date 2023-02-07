<template>
  <div>
    <Section>
      <Button />
    </Section>
    <RemoteSection>
      <RemoteButton msg="test props" @increase="getCounter" />
    </RemoteSection>
  </div>
</template>

<script lang="ts">
import {Vue, Component } from "vue-property-decorator";
import Section from './components/Section.vue'
import RButton from 'remote-simple/remote-simple-button';
import RSection from 'remote-simple/remote-simple-section'
import Button from './components/Button.vue'

@Component({
  components: {
    Section,
    Button,
    RemoteButton: RButton,
    RemoteSection: RSection
  }
})
export default class App extends Vue {
  public getCounter(count: number) {
    console.log(count);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
