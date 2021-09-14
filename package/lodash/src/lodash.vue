<template>
  <div class="lodash__content">
    <ui class="func">
      <li v-for="(item,key) in func" class="func__item">
{{item.name}}
      </li>
    </ui>
    
  </div>
</template>
<script>
  export default {
      name: 'HLodash',
data(){
return{
  func:[]
}
},
    props: {

    },

    computed: {
      buttonSize() {
        return this.size;
      },
      buttonDisabled() {
        return this.disabled;
      }
    },
    mounted() {
      let _ = require('lodash');

      for (const key in _) {
        if (Object.hasOwnProperty.call(_, key)) {
          this.func.push({name:key})
          console.log(key);

        }
      }
    },
    methods: {
      handleClick(evt) {
        this.$emit('click', evt);
      }
    }
  };
</script>
<style lang="less" scoped>

</style>
