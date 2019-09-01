
    整理思路
1. new Vue => this._init => src/core/instance/init.js
2. const mount = proptype.$mount 缓存
3. Vue.proptype.$mount 加上一系列判断,然后调用template or el 生成render，staticRender 挂到 vm 上
4. mount() => 调用render生成vnode watch中调用_update => _patch 挂载到dom 期间调用了mounted的钩子 mount(定义在 src/platform/web/runtime/index.js)
()
***********************第三章****************************
4. createElement  => 其中返回vnode ，Ctor 是一个基于VUE的子类构造器, installComponentHooks之后给data附上了hook,返回vnode,vnode中有一个基于vue的子类构造器(构造子类构造函数，安装组件钩子函数和实例化 vnode)

5.patch=>createElm=>createComponent(判断)
  vnode =>组件vnode(展位vnode)(生成new Ctor) =>组件vnode的渲染vnode(createElm的时候插入到父类)=>组件vnode(展位vnode)(createComponent中插入父类)=>vnode挂载到html文件

  挂载顺序是先子后父，从上到下





问题
$options中都有啥 new Vue的时候传入的参数和原本就设定好的一些参数
data中都有啥(vnode) 组件的时候有hooks，非组件的时候是html上的属性啥的

组件挂载的实现和关系已经弄懂

响应式？
指令？
template？
