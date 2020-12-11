<template>
  <button @click="count++">count为：{{ count }}</button>
</template>
<script>
import { ref, watch, watchEffect } from "vue";
export default {
  setup() {
    let count = ref(1);
    //第一种watchEffect ，只要里面的变量发生改变就会执行，并且第一次渲染会立即执行
    watchEffect(() => {
      console.log("count", count.value);
    });
    //watch里第一个参数是需要监听的变量，第二个参数是执行的回调函数
    watch(count, (newValue, odValue) => {
      console.log("count", count.value);
    });
    return {
      count,
    };
  },
};
// export default {
//   data() {
//     return {
//       count: 0
//     }
//   },
//   watch:{
//     count:{
//       handler: function(newVal, oldVal){
//         console.log('newVal', newVal)
//       }
//     }
//   }
// }
</script>
