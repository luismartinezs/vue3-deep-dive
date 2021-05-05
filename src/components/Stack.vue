<script>
import { h } from "vue";

export default {
  name: "Stack",
  props: {
    size: {
      type: [Number, String],
      default: 4,
    },
  },
  render() {
    const rem = Math.round(this.$props.size / 4);
    const slot = this.$slots.default ? this.$slots.default() : [];

    return h(
      "div",
      {
        class: "stack",
      },
      slot.map((child) => {
        return h(
          "div",
          {
            style: `margin-left: ${rem}rem;`,
          },
          child
        );
      })
    );
  },
};
</script>