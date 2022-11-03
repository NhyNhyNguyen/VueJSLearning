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
####
- @submit.prevent: prevent chặn các default event -> case này chặn default event reload page khi submi
### Custom Component 
- Dưới phần khai báo của vue component 
- Trên mounted
Noted: 
- @submit : khi click form sẽ auto reload form. Là action auto browser
- case bắt sự kiện trong multiselect ????
```
  app.component(
            "custom-form",{
                template:`
                    <form @submit.prevent="handleSubmit">
                    <h1>
                      {{ title }}
                    </h1>
                        <input type = 'email'/>
                        <input type = 'password'/>
                    <button type="submit">Submit</button>
                    </form>
                `,
                data: function (){
                    return {
                        title: "Login Form"
                    }
                },
                methods:{
                    handleSubmit:function (){
                        console.log("Submit")
                    }
                }
            },

        )
```

#### Component pr
- pass data from parent component to child component
```
    <custom-input  v-model="email" :model-value="email" v-bind:label="emailLabel"/>
```
- using v-bind to pass data from variable emailLabel to label
- v-blind: cũng có thể use :
- user *props* in child component list all things passing from parent to child
```
   props:['label','modelValue'],
```
#### Component compute
- pass data from child component to parent component
- user *$emit => ????
- computed: object U can put variable name at key, and whatever that value changed it can run getter and setter
```
 inputValue:{
                        get(){
                            return this.modelValue;
                        },
                        set(value){
                            this.$emit('update:modelValue', value)
                        }
                    }
```
```
 app.component(
            "custom-input",{
                template:
                    `
                <label>
                    {{label}}
                    <input type="text" v-model="inputValue"/>
                </label>
                `,
                props:['label','modelValue'],
                computed:{
                    inputValue:{
                        get(){
                            return this.modelValue;
                        },
                        set(value){
                            this.$emit('update:modelValue', value)
                        }
                    }
                }
                // data:{
                //     inputValue: ""
                // }
            }
        )
```



