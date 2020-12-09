<template>
  <div class="hello">
    Base
    <slot />
    <!-- Here we create two different slots so we can see what's going on -->
    <strong>
      <slot name="strong" />
    </strong>
    <em>
      <slot name="emphasis" />
    </em>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>