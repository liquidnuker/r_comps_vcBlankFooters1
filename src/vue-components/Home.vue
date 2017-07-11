<template>
  <div class="row">
    <!-- begin BlankFooter1 placeholder -->
    <h2 class="item-id">BlankFooter1</h2>
    <!-- BlankFooter1 -->
    <!-- end BlankFooter1 -->
    <div id="vc_BlankFooter1_mount">
    </div>
    <!-- end BlankFooter1 placeholder -->
    <!-- begin BlankFooter1 placeholder -->
    <h2 class="item-id">BlankFooter2</h2>
    <!-- BlankFooter1 -->
    <!-- end BlankFooter1 -->
    <div id="vc_BlankFooter2_mount">
    </div>
    <!-- end BlankFooter1 placeholder -->
  </div>
</template>
<script>
import {inject} from "../js/componentinjector.js";
  export default {
    data () {
      return {    
      }
    },
    mounted: function () {
      console.log("Home.vue mounted");
      this.mountBlankFooter1()
    },
    methods: {
      mountBlankFooter1: function() {
        const BlankFooter1 = resolve => {
          require.ensure(['./BlankFooter1.vue'], () => {
            resolve(require('./BlankFooter1.vue'))
          })
        };
        inject("#vc_BlankFooter1_mount", BlankFooter1);
        this.mountBlankFooter2();
      },
      mountBlankFooter2: function() {
        const BlankFooter2 = resolve => {
          require.ensure(['./BlankFooter2.vue'], () => {
            resolve(require('./BlankFooter2.vue'))
          })
        };
        inject("#vc_BlankFooter2_mount", BlankFooter2);
      }
    }
  }
</script>