>###1. 声明式绑定
>>数据绑定  (vue实例中的data，computed)
>>>插入值绑定
>>>######使用Mustache语法设置绑定。Mustache代表的就是双大括号({{}})
>`<span>{{message}}</span>`
>>>######插入值绑定将会把数据对象上的属性值插入到Mustache指示的位置，且绑定的数据对象的变化会导致插值的变化。
>>> ######如果数据成员内容是HTML片段，并且希望插入这个片段到DOM内，那么使用指令v-html，使用v-html动态渲染用户提供的内容插值需要小心，至少不要把用户输入内容作为值来插入，否则很容易导致XSS攻击。
>>>######插入值绑定是无法处理HTML元素属性的
>`<input value="{{value}}">`错
>`<input :value="value">` 对
>`<input v-bind:value="value">` 对

> >事件绑定 (vue实例中的methods)
> >>######指令v-on可以监听DOM事件
> `<button v-on:click="add">add</button>`
> `<button @click="add">add</button>`
> `<input @keyup.enter="add">add</button>`

> >元素绑定
> >>######比如根据表达式条件的不同来绑定不同的元素，或者循环绑定元素。
> `<h1 v-if="true">h1</h1>`
> `<ul>`
    `<li v-for="(item, index) in items">{{item}}</li>`
    `</ul>`

>>控件绑定
>>>######绑定表单控件和绑定普通组件并无二致。但是因为控件绑定常常涉及到双向绑定，此时使用v-model让它更加简单。
>`<label><input type="checkbox" v-model="checked">{{checked?'勾上了':'未勾上'}}</label>`

---
>###2. 基于组件的编程
>>vue实例
>>指令
>>>######带有v-前缀的特殊HTML标签属性。指令的职责，就是当其属性值改变时，将某些行为应用到DOM上

>>>######指令能接受一个参数，在指令后以“:”指明。
>>>######指令能接受一个或者多个修饰符，是以“.”指明的特殊后缀。
>>>######指令能接受一个单一JavaScript表达式，最常见的表达式就是一个属性值
>>>######可以自定义指令
>>...

----
data函数成员
methods对象成员
模板template
挂载元素el
生命周期钩子
props属性声明
computed计算成员
watch监视成员
