<template>
  <!-- This component acts exactly like the `Base` component, but also grabs
       all of the slots from the parent. This way we don't have to do anything
       to pass slots through this component to it's child. -->

  <!--
      Grandparent -> Parent -> Child 
        `strong` ==>==>==>==>===x
                  `emphasis` ===x

      The `strong` slot is created in the Grandparent component but is applied to the
      Child component. At the same time, we can still create a slot in the Parent
      component and apply it to the Child like we normally would.
  -->
  <Passthrough :component="Base">
    <template #emphasis>Middle</template>
  </Passthrough>
</template>

<script>
import Base from "./Base";
import Passthrough from "./Passthrough";

export default {
  components: { Passthrough },
  data() {
    return {
      Base,
    };
  },
};
</script>

