<template>
  <label
    :for="id"
    :aria-label="ariaLabel"
    :aria-expanded="ariaExpanded"
    role="button"
    tabindex="0"
    class="vue-cool-burger"
    :style="styles"
  >
    <input
      :id="id"
      aria-hidden="true"
      type="checkbox"
      :checked="ariaExpanded"
    />
    <span aria-hidden="true"></span>
    <span aria-hidden="true"></span>
    <span aria-hidden="true"></span>
  </label>
</template>

<script>
/*
 * Component by Javad Mnjd
 * Original idea by Erik Terwan
 * 31th of December 2020
 * MIT License
 */

export default {
  props: {
    color: {
      type: String,
      default: '#cdcdcd',
    },
    crossColor: {
      type: String,
      default: '#cdcdcd',
    },
    id: {
      type: String,
      default: undefined,
    },
    ariaLabel: {
      type: String,
      default: 'main menu',
    },
    expanded: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      ariaExpanded: false,
    };
  },
  computed: {
    styles() {
      return {
        '--burger-color': this.color,
        '--burger-cross-color': this.crossColor,
      };
    },
  },
  created() {
    this.ariaExpanded = this.expanded;
  },
  methods: {
    toggleExpand() {
      this.ariaExpanded = !this.ariaExpanded;
      if (this.ariaExpanded) {
        this.$emit('expanded', this.ariaExpanded);
      }
    },
  },
};
</script>

<style lang="css">
.vue-cool-burger {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: space-around;
  user-select: none;

  width: 100%;
  height: 100%;
}

.vue-cool-burger input {
  display: none;
}

/*
* a quick hamburger
*/
.vue-cool-burger span {
  display: block;
  margin: 0 auto;
  width: 90%;
  height: calc(100% / 9);

  background: var(--burger-color);
  border-radius: 999px;

  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
    background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
}

.vue-cool-burger input:checked ~ span {
  opacity: 1;
  background: var(--burger-cross-color);
}

/*
  *  hide middle one.
  */
.vue-cool-burger input:checked ~ span:nth-of-type(2) {
  opacity: 0;
  transform: scale(0.2, 0.2);
}

.vue-cool-burger input:checked ~ span:first-of-type {
  transform: translate(0, 300%) rotate(45deg);
}

.vue-cool-burger input:checked ~ span:last-of-type {
  transform: translate(0, -300%) rotate(-45deg);
}
</style>
