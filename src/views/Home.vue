<template>
  <div class="home">
    <sticky-header />
    <b-container class="button-header align-content-end" >
      <b-row align-h="end">
        <b-button variant="primary" @click="add('primary')">+</b-button>
        <b-button variant="secondary" @click="add('secondary')">+</b-button>
        <b-button variant="info" @click="add('info')">+</b-button>
        <b-button variant="warning" @click="add('warning')">+</b-button>
        <b-button variant="danger" @click="add('danger')">+</b-button>
        <b-button variant="dark" @click="add('dark')">+</b-button>
      </b-row>
    </b-container>

    <b-container fluid>
      <b-row>
        <component
          v-for="(component, indx) in components"
          :key="indx"
          :is="'SingleSticky'"
          :color="component.color"
          @clickdelete="DeleteSingleSticky(indx)"
        />
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
import StickyHeader from "@/components/StickyHeader.vue";
import SingleSticky from "@/components/SingleSticky.vue";

export default {
  name: "Home",
  components: {
    StickyHeader,
    SingleSticky,
  },
  data() {
    return {
      comp: {
        id: null,
        color: "",
        textcolor: "",
      },
      components: [],
    };
  },
  methods: {
    add(color, id) {
      this.comp.color = color;
      this.comp.id = id;
      this.components.push(this.comp);
      this.comp = { color: "", textcolor: "", id: null };
    },
    DeleteSingleSticky(indx) {
      this.components.splice(indx, 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.button-header {
  .btn {
    margin: 20px 3px;
    border-radius: 50%;
  }
}
</style>
