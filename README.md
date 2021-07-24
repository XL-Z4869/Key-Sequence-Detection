# Key-Sequence-Detection
输入‘hello’，会随机显示图标<a href="https://xl-z4869.github.io/Key-Sequence-Detection/index.html">效果链接</a>
 

知识点主要是对数组的使用
### 步骤
#### 1.定义两个变量，一个作为密码‘hello’，一个记录键盘按下记录
```
 const press = []
 const secretCode = 'hello'
```
#### 2.绑定事件
* 记录键盘事件，并将key值push到数组中
* 使用splice，确保输入跟'hello'一样长的数组之后，要开始删除第一个
* 之后再进行判断是否存在密码‘hello’
```
 window.addEventListener('keyup', (e) => {
    console.log(e);
    press.push(e.key)
    press.splice(0, press.length - secretCode.length)
    if (press.join('').includes(secretCode)) {
       cornify_add();
    }
    console.log(press);
})
```
