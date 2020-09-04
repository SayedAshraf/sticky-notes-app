<template>
  <div class="Sticky">
      <b-card text-variant="white" :class="['text-center', `bg-${color}`, `text-${textcolor}`]" >
        <template v-slot:header>
          <b-button class="del-btn" variant="light" @click="$emit('clickdelete')">X</b-button>
        </template>
            <vue-editor v-model="content"></vue-editor>
    </b-card>
  </div>
</template>

<script>
import { VueEditor } from "vue2-editor";

export default {
  name: "SingleSticky",
  components: {
    VueEditor
  },
    data() {
        return {
        content: ""
        };
    },
  props: {
    color: {
      type: String,
      required: true,
      default: "Default",
      validator: function(value) {
        return (
          ["Default","primary","secondary","success","info","warning","danger","light","dark",].indexOf(value) !== -1
        );
      },
    },
    textcolor: {
      type: String,
      required: false,
      default: "white",
      validator: function(value) {
        return ["white", "black", "secondary"].indexOf(value) !== -1;
      },
    },
  },
};
</script>
<style lang="scss" scoped>
.Sticky {
  margin: 5px;
  width: 500px;
  .del-btn{
      float: right;
      border-radius: 50%;
  }
}
</style>
