# mvvm
## 简介：
MVVM 依次就是 **Model** **View** **ViewModel**  
**Model**:dep.ts  
**View**:demo.html  
**ViewModel**:compiler.ts、index.ts、observer.ts、watcher.ts  
## 使用方式：
直接运行 demo.html  
## 主要功能：
### 数据劫持：
每个组件实例都对应一个 watcher 实例，它会在组件渲染的过程中把“接触”过的数据属性记录为依赖  
之后当依赖项的 setter 触发时，会通知 watcher，从而使它关联的组件重新渲染。
### 发布订阅模式：
Observe扮演的角色是发布者，对对象的每一个属性进行数据监听  
Watcher是连接组件和data的桥梁  
Dep则扮演是一个收集依赖和管理通知更新的调度中心
### 单向数据绑定:
Model层的数据变化时会导致View的数据变化，但是View的数据变化并不会引起Model层的数据变化  
在这里单向数据流涉及到了Object.defineProperty()这个方法  
它可以监听变量的读取和写入并在发生读取与写入的时候执行回调函数
### 双向数据绑定：
通过input事件来监听用户行为，一旦触发了Input事件，content的值也随即会发生变化  
也就是View中的数据变化导致Model层的数据变化  
而在data中去声明的content的值，也会导致value值的变化  
也就是Model层的数据变化导致View的数据变化
