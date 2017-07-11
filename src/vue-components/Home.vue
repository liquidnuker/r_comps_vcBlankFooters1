<template>
  <div class="row">
    <!-- begin FooterBlanks1 placeholder -->
    <h2 class="item-id">FooterBlanks1</h2>
    <!-- FooterBlanks1 -->
    <!-- end FooterBlanks1 -->
    <div id="vc_FooterBlanks1_mount">
    </div>
    <!-- end FooterBlanks1 placeholder -->
    <!-- begin FooterBlanks1 placeholder -->
    <h2 class="item-id">FooterBlanks2</h2>
    <!-- FooterBlanks1 -->
    <!-- end FooterBlanks1 -->
    <div id="vc_FooterBlanks2_mount">
    </div>
    <!-- end FooterBlanks1 placeholder -->
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
      this.mountFooterBlanks1()
    },
    methods: {
      mountFooterBlanks1: function() {
        const FooterBlanks1 = resolve => {
          require.ensure(['./FooterBlanks1.vue'], () => {
            resolve(require('./FooterBlanks1.vue'))
          })
        };
        inject("#vc_FooterBlanks1_mount", FooterBlanks1);
        this.mountFooterBlanks2();
      },
      mountFooterBlanks2: function() {
        const FooterBlanks2 = resolve => {
          require.ensure(['./FooterBlanks2.vue'], () => {
            resolve(require('./FooterBlanks2.vue'))
          })
        };
        inject("#vc_FooterBlanks2_mount", FooterBlanks2);
      }
    }
  }
</script>