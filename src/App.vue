<template>
  <div id="app">
    <div class="row margin-top-medium">
      <button class="btn btn--blue" @click="activateComponent('blue')">Load Blue Template</button>
      <button class="btn btn--green" @click="activateComponent('green')">Load Green Template</button>
      <button class="btn btn--red" @click="activateComponent('red')">Load Red Template</button>
    </div>

    <hr class="margin-top-big">

    <div class="row margin-top-medium">
      <component :is="componentActivated">
          <h2 :class="componentHeading" slot="heading" :componentHeading = "componentHeading">{{ headingText }}</h2>
          <p :class="componentContent" slot="content">{{ paragraphText }}</p>
      </component>
      <!-- <component :is=" 'app-green' ">
        <h2 class="heading-green" slot="heading-green">Hello, I am a green component</h2>
        <p class="content-green"  slot="content-green">Here goes green component text</p>
      </component>
      <component :is=" 'app-red' ">
        <h2 class="heading-red" slot="heading-red">Hello, I am a red component</h2>
        <p class="content-red" slot="content-red">Here goes red component text</p>
      </component> -->

    </div>
  </div>
</template>

<script>

  import Blue from './components/Blue.vue';
  import Green from './components/Green.vue';
  import Red from './components/Red.vue';

  export default {

    data: function() {
      return {
         componentActivated: null,
         componentHeading: {
            'heading_blue': false,
            'heading_green': false,
            'heading_red': false,
         },

         componentContent: {
            'content_blue': false,
            'content_green': false,
            'content_red': false,
         },

          headingText: '',
          paragraphText: ''
      }
    },

    components: {
      'app-blue': Blue,
      'app-green': Green,
      'app-red': Red
    },

    methods: {
      activateComponent(component) {
        if (component === 'blue') {
          this.componentActivated = 'app-blue';
          this.componentHeading.heading_blue = true;
          this.componentContent.content_blue = true;
          this.headingText = 'Hello, I am a blue component';
          this.paragraphText = 'Here goes blue component text';

        } else if (component === 'green') {
          this.componentActivated = 'app-green'
          this.componentHeading.heading_green = true;
          this.componentContent.content_green = true;
          this.headingText = 'Hello, I am a green component';
          this.paragraphText = 'Here goes green component text';

        } else if (component === 'red') {
          this.componentActivated = 'app-red'
          this.componentHeading.heading_red = true;
          this.componentContent.content_red = true;
          this.headingText = 'Hello, I am a red component';
          this.paragraphText = 'Here goes red component text';

        }
      }
    }

}
</script>

<style lang="scss">

// UTILITY CLASSES
.margin-top-small {
  margin-top: 1rem !important;
}

.margin-top-medium {
  margin-top: 2rem !important;
}

.margin-top-big {
  margin-top: 3rem !important;
}

  html {
    box-sizing: border-box;
    font-size: 62.5%;
  }

  *, *:before, *::after {
    box-sizing: inherit;
  }

  .row {
    width: 80%;
    margin: 0 auto;
  }

  .btn {

    width: 150px;
    line-height: 2;
    margin: 0 .2rem;
    border: none;
    border-radius: .3rem;

    font-size: 1.3rem;
    font-weight: 600;
    color: #fff;
    cursor: pointer;


    &--blue {
      background-color: rgba(blue, .8);

      &:hover {
      background-color: rgba(blue, 1);
      }

    }

    &--green {
      background-color: rgba(green, .8);

      &:hover {
      background-color: rgba(green, 1);
      }
    }

    &--red {
      background-color: rgba(orangered, .8);;

      &:hover {
      background-color: rgba(orangered, 1);
      }
    }
  }

  .component {

    height: 10rem;
    padding: .5rem;
    border: 1px solid #666;
    margin-bottom: 3rem;
    box-shadow: 1rem 1rem 2rem rgba(#000, .7);
  }


</style>
