<template>
  <touch-verify-code @success="onSuccess"
                     @failed="onFailed" />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TouchVerifyCode from "@/components/TouchVerifyCode.vue";

const App = defineComponent({
  name: "App",
  components: {
    TouchVerifyCode,
  },
  setup() {
    const onSuccess = (time: number) => {
      console.log("验证成功", time);
    };

    const onFailed = () => {
      console.log("验证失败");
    };

    return { onSuccess, onFailed };
  },
});

export default App;
</script>
