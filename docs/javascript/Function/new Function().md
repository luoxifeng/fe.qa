# new Function()

## 尽量不要new Function()
  - 性能
    ```
    参数以字符串的形式传递并重新计算，类似的有eval('xxxxx')，setTimeourt('xxxxx')；
    就像我们被建议不要这样使用eval，setTimeout一样，
    以new Function()这种形式创建函数同样是不推荐的(除了特殊场景下，你不得不)
    ```
    可以用以下两端代码来测试两种创建函数的性能对比
    ```javascript
    console.time();
    let i = 0;
    while (i++ < 1000) {
        new Function('');
    }
    console.timeEnd();
    ```
    ```javascript
    console.time();
    let i = 0;
    while (i++ < 1000) {
        function test(){};
    }
    console.timeEnd();
    ```
    进过对比在创建1000词函数的结果中，他们的差距是200+倍
  - 可读性
    ```
    出于可读性的目的我们希望函数体中代码能保持相应的缩进，在字符串中保持缩进并不是很好的实践
    ```
