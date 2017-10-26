# Emitter

## 概述

事件发射器

## 背景

JS 程序中存在大量的异步程序，采用 callback 的写法会面临回调地狱的噩梦，且会造成代码强耦合，代码会变得越来越难维护。

## 用法

```javascript
var emitter = new Emitter();

emitter
  .on('eventA', fnA)
  .on('eventB', fnB)
  .once('eventC', fnC)
  .off('eventB', fnB)
  .emit('eventA', args)
```

## 实例属性和方法

### **emitter.on(eventName, listener)**

别名：emitter.addListener(evenetName, listener)

事件注册函数，listener 为匿名函数时无法移除

### **emitter.once(eventName, listener)**

事件注册函数，只会执行一次

### **emitter.off(eventName, listener)**

别名：emitter.removeListener(evenetName, listener)

事件移除函数，无法移除匿名函数

### **emitter.emit(eventName[, ...args])**

别名：emitter.dispatchEvent(evenetName[, ...args])

事件分发函数，支持传入多个参数
