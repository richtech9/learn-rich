<template>
  <div class="u-section-padding u-bg-gray u-fill-viewport-gap">
    <div class="c-sidenav">
      <ul>
        <li 
          @click="selectedComponent = 'Introduction'"
          :class="{active: selectedComponent === 'Introduction'}"
          >Introduction</li>
        <li 
          @click="selectedComponent = 'DataTypes'"
          :class="{active: selectedComponent === 'DataTypes'}">Data Types</li>
        <li 
          @click="selectedComponent = 'Strings'"
          :class="{active: selectedComponent === 'Strings'}">Strings</li>
        <li 
          @click="selectedComponent = 'Functions'"
          :class="{active: selectedComponent === 'Functions'}">Functions</li>
        <li 
          @click="selectedComponent = 'Arrays'"
          :class="{active: selectedComponent === 'Arrays'}">Arrays</li>
        <li 
          @click="selectedComponent = 'Objects'"
          :class="{active: selectedComponent === 'Objects'}">Objects</li>
        <li 
          @click="selectedComponent = 'JSON'"
          :class="{active: selectedComponent === 'JSON'}">JSON</li>
        <li 
          @click="selectedComponent = 'UnderTheHood'"
          :class="{active: selectedComponent === 'UnderTheHood'}">Under the hood concepts</li>
        <li 
          @click="selectedComponent = 'ClientSideJS'"
          :class="{active: selectedComponent === 'ClientSideJS'}">Client Side JavaScript</li>
        <li 
          @click="selectedComponent = 'AsyncJS'"
          :class="{active: selectedComponent === 'AsyncJS'}">Asynchronous JavaScript</li>
        <li 
          @click="selectedComponent = 'Resources'"
          :class="{active: selectedComponent === 'Resources'}">Resources</li>
      </ul>
    </div>
    <div class="l-wrap">
      <div class="l-row">
        <div class="l-col l-col--md-10 l-col--offset-md-1">

          <!-- Back Home -->
          <router-link :to="{ name: 'Home' }" class="u-top-el">Back home</router-link>

          <!-- Render different component dynamically -->
          <component :is="selectedComponent"></component>

        </div><!-- /.l-col -->
      </div><!-- /.l-row -->
    </div><!-- /.l-wrap -->
  </div>
</template>

<script>
  import Arrays         from '../components/Arrays'
  import AsyncJS        from '../components/AsyncJS'
  import ClientSideJS   from '../components/ClientSideJS'
  import DataTypes      from '../components/DataTypes'
  import Functions      from '../components/Functions'
  import Introduction   from '../components/Introduction'
  import JSON           from '../components/JSON'
  import Objects        from '../components/Objects'
  import Resources      from '../components/Resources'
  import Strings        from '../components/Strings'
  import UnderTheHood   from '../components/UnderTheHood'

  export default {
    name: 'JavaScript',
    data() {
      return {
        selectedComponent: 'Introduction'
      }
    },
    components: {
      Arrays,
      AsyncJS,
      ClientSideJS,
      DataTypes,
      Functions,
      Introduction,
      JSON,
      Objects,
      Resources,
      Strings,
      UnderTheHood
    },
    mounted() {
      window.Prism.highlightAll()
    }
  }
</script>