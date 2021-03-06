# <div align="center">Vue - ie9 兼容</div>

**背景情况**
- vue2.5.11
- vue-cli 使用模板 `webpack-simple`

## 目录

- [es6](#es6)
- [Number对象](#Number对象)
- [http网络请求(跨域)](#http网络请求(跨域))

<br><br><br><br><br><br>

## es6

在使用 Vue 做项目开发时，
```html
<user v-for="user, index in users"      
      :key="'user-' + user.id"
      >
```
在使用自定义组件，并需要生成多个时，有个很重要的属性需要关注：`key`

使用中可以把它理解成组件的唯一 id，建议在绑定时，绑定一些不会重复的自定义值，注意不要使用 `v-for` 中的 `index` 属性进行绑定，这个 `index` 就是数组的下标，在频繁增加、移除时，数组下标会出现重复。

期望的结果是移除最后一个组件，并新增一个新的组件；此时，被移除的组件下标是0，新增的组件下标也是0，Vue 会认为现有的组件内容需要更新，而不是去新增一个新的组件，这样常常会出现莫明其妙的问题

<br><br>

## Number对象

## http网络请求(跨域)

<br><br>
