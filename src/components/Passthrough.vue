<script>
export default {
  name: "Passthrough",

  props: {
    component: {
      type: Object,
      required: true,
    },
  },

  render(h) {
    const slots = {
      // Grab slots from parent to pass through
      ...this.$parent.$slots,

      // Allow slots defined on this component to override it as well
      ...this.$slots,

      // If we wanted we could walk up the entire ancestry of this component
      // and grab *any* slots that have matching names to what our component
      // has defined. This would create a system similar to `provide` and `inject`
      // but for slots.
    };

    // Create mappings to extend our component
    const slotMap = Object.keys(slots).map((key) => ({
      key,
      fn: () => slots[key],
      proxy: true,
    }));

    // Render component with extended slots
    return h(this.component, {
      scopedSlots: this._u(slotMap),
    });
  },
};
</script>
