# Vue3 Slide Verify Code
> Vue3 滑块验证码

## 参数

| 参数          | 类型                              | 默认值                                 | 说明                                              |
| ------------- | --------------------------------- | -------------------------------------- | ------------------------------------------------- |
| containerSize | `{width: number, height: number}` | `{width: 400, height: 250}   `         | 容器大小                                          |
| slideSize     | `number`                          | `56`                                   | 滑块卡片的大小                                    |
| slideRadius   | `number`                          | `10`                                   | 滑块卡片的圆圈半径                                |
| accuracy      | `number`                          | `5`                                    | 机器验证精确度，-1表示不验证是否机器              |
| barText       | `[string, html]`                  | "&lt;&lt; 按住滑块，向右拖动 &gt;&gt;" | 滑块提示语                                        |
| resource      | string[]                          | `[]`                                   | 图片资源，默认使用`https://picsum.photos`上的资源 |

## 使用
```html
<template>
  <touch-verify-code @success="onSuccess"
                     @failed="onFailed"
                     @refresh="onRefresh" />
</template>

<script>
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

    const onRefresh = () => {
      console.log("图片刷新成功")
    }

    return { onSuccess, onFailed, onRefresh };
  },
});

export default App;
</script>
```

## 效果

[效果展示](http://normal-image.xiaovv-web.com/normal/2020-12-08-verify-code-gif.gif)

## TODO
 - npm
 - 测试

## 感谢
项目借鉴[monoplasty](https://github.com/monoplasty/vue-monoplasty-slide-verify)