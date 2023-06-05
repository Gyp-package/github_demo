# github_demo  用户搜索案例

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

1.bootstrap 作为第三方库一般不放在 App.vue（一般放手写css）中，便于升级
2.使用axios返回响应数据
3.使用全局事件总线，
4.List展示功能：
网络慢时欢迎词填补空白，
搜索时加载字体，
users图片，
error错误