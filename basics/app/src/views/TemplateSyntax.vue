<script lang="ts">
  export default {
    data() {
      return {
        dynamicHTML: `<code>Dynamic HTML</code>`,
        isButtonDisabled: false,
      }
    },
    methods: {
      handleCheckboxState(event: any) {
        console.log({isChecked: event.target.checked});
        this.isButtonDisabled = event.target.checked;
      },
      handleCTAClick(event: any) {
        console.log('CTA clicked!', event);
      }
    },
  }
</script>
<template>
  <div class="template-syntax">
    <h1 :id="'title'">{{ 'Template Syntax:' }}</h1>
    <p class="wrapper" v-html="dynamicHTML"></p> <!-- will PARSE as HTML --> 
    <p>{{ dynamicHTML }}</p> <!-- will NOT parse as HTML -->
    <button :disabled="isButtonDisabled" @click="handleCTAClick">Call to action</button>
    <input type="checkbox" name="cta" :id="'ctaChackbox'" v-on="{ change: handleCheckboxState }" />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
