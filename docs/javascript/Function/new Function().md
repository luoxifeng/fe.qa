# new Function()

## 尽量不要new Function()
  - 性能
  ```
  参数以字符串的形式传递并重新计算，类似的有eval('xxxxx')，setTimeourt('xxxxx')；
  就像我们被建议不要这样使用eval，setTimeout一样，
  以new Function()这种形式创建函数同样是不推荐的(除了特殊场景下，你不得不)
  ```
  - 可读性
  ```
  出于可读性的目的我们希望函数体中代码能保持相应的缩进，在字符串中保持缩进并不是很好的实践
  ```
