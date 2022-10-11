## Vue JS
### Install vuejs 3
https://vuejs.org/guide/quick-start.html#using-vue-from-cdn
#### Use vs code: 
- install plugin live server
### Syntax
- create vue objec
```
 <script>
        let app = Vue.createApp({
            data: function (){
                return {
                    greeting: "Hello Vue 3!",
                    isVisible: true,
                }
            }
        })
        app.mount("#app");
    </script>
```
#### v-model: bind to variable
#### v-if: set false remove from done
- v-else-if
- v-else
- v-show: giống với v-if nhưng mà ở phần code render ra sẽ có chỉ là style= "display: none"
=> trường hợp nào nên dùng show, if: need use frequent -> hiệu quả hơn là remove rùi add
#### v-cloak
- Hide any thing from rendering until whole vue application is ready
- When vue load have done v-cloak have removed
### Event - Method
- Many events that can be capture in browser and use in application: press key, click button 
#### v-on
- v-on:click -> @click 
- ontoggle:function (){} -> ontoggle(){}
- this: vue put all methods, variable in this
#### @keyup:
- @keyup.enter="greet" -> @keyup.13 => đợi sự kiện có enter => call greet
- @keyup.enter="greet(greeting)" => có thể passing biến
#### @click.right
- @click.prevent.stop
### Custom Component 
