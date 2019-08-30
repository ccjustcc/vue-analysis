
    整理思路
1. const mount = proptype.$mount 缓存
2. Vue.proptype.$mount 加上一系列判断,然后调用template or el 生成render，staticRender 挂到 vm 上
3. mount() => 调用render生成vnode watch中调用_update => _patch 挂载到dom 期间调用了mounted的钩子 mount(定义在 src/platform/web/runtime/index.js)
***********************第三章****************************
4. createElement  => 其中返回vnode ，Ctor 是一个基于VUE的子类构造器, installComponentHooks之后给data附上了hook,返回vnode,vnode中有一个基于vue的子类构造器(构造子类构造函数，安装组件钩子函数和实例化 vnode)