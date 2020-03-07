### 微信小程序
- 具有Vue的模板化思想和react的状态机机制


#### Taro框架
- 一套代码多端运行
   + 微信小程序
   + 百度小程序
   + 支付宝小程序
   + web(h5)
   + ReactNative
- 遵循jsx规范
- 支持组件化
- 支持Typescript

##### 安装
> npm install -g @tarojs/cli

##### 初始化
> taro init your_app_name

##### 启动命令
###### h5
> npm run dev:h5
###### 微信小程序
> npm run dev:weapp
###### 支付宝小程序
> npm run dev:alipay
###### 百度小程序
> npm run dev:swan
###### ReactNative
> npm run dev:rn

#### 注意
- Taro中父组件传递给子组件的事件名需用`on`开头，采用驼峰命名，若需要阻止冒泡，需明确使用`stopPropagation`
- Taro中的页面跳转最多嵌套5层
- Taro样式中小写单位`px`会自动转换成`rem`,若需要使用像素单位，需要用大写`PX`
- Taro中的`this.props.children`是只读的，不能进行其他任何操作
- Taro中事件绑定无法使用箭头函数，需要使用`bind`,事件方法的参数最后一个是`event`
- Taro中样式无法使用id选择器、标签选择器、属性选择器、子选择器
- 建议使用Flex布局，适配小程序和h5

#### 路由
- 路由的参数在跳转成功的目标页的componentWillMount生命周期里获取

#### 补充
- Taro中可像webpack那样自由的引用静态资源，且不需要安装任何loader
- `process.env.TARO_ENV`标识当前环境（只在开发阶段使用），可以在不同的环境下，渲染不同的样式