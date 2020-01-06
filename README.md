# flex.css

项目来源 [https://github.com/lzxb/flex.css](https://github.com/lzxb/flex.css) 有兴趣可以移步去看一下。
本项目主要喜欢上面项目布局的方式，但是又不习惯他定义的名称，所以改写了一下。

### 下载
```
git clone https://github.com/Autumn-Seven/flex.css.git
```

### 安装
```
npm install Autumn-Seven/flex.css --save
@import "flex.css";
```


### 为什么使用 flex?
```
简洁的api，熟悉的属性值，入门毫无压力。
在html中采用属性的方式布，将布局和css进行分离，清晰的布局结构让你更容易维护，可以在不更改css的情况下更改布局。
特别是在React中使用data-flex属性布局，维护起来更加的方便。
```



### 兼容性
```
flex layout is split into three versions: old version: display: box; , transitional version: display:flexbox; ,
and present standard version: display:flex; .
Android
2.3  began to support old version: display: -webkit-box;
4.4 began to support standard version: display: flex;
IOS
6.1  began to support old version: display: -webkit-box;
7.1 began to support standard version: display: flex;
PC
You can use flex.css if you don't need to consider IE10-.
flex.css is compatible with standard version and old version at the same time, so when a browser doesn't support standard version, it will roll back to old version.

```
![Alt text](https://github.com/lzxb/flex.css/raw/master/shot/caniuse.png)

### 使用方法
```html
<!--
According to what you need, include css files in the dist directory into your html
flex.css should be matched by flex attribute
data-flex.css should be matched by data-flex attribute(used by React)
If you use webpack to package, after npm is installed, and ES6 compiler is deployed in your project,
flex attribute matching can be implemented in this way:
import 'Autumn-flex/dist/flex.css';
data-flex attribute matching can be implemented in this way( used by React):
import 'Autumn-flex/dist/data-flex.css';
 -->
<!-- flex attribute matching，a simple example of centering child element ： -->
  <div flex="main:center cross:center" style="width:500px; height: 500px; background: #108423">
    <div style="background: #fff"> to see if this is in the center </div>
  </div>

<!-- data-flex attribute matching，a simple example of centering child element： -->
  <div data-flex="main:center cross:center" style="width:500px; height: 500px; background: #f1d722">
    <div style="background: #fff"> to see if this is in the center </div>
  </div>
```
### 属性介绍
```
dir: 方向 flex-direction
    left：从左到右( default )
    top：from top to bottom
    right：from right to left
    bottom：from bottom to top
    
```
```
wrap: 是否换行 flex-wrap: nowrap;
    nowrap：from top to bottom (默认不换行)
    start：换行，从左到右排列
    end：换行，从右到左排列  
```


```
main：主轴对齐方式 justify-content
    start：从左到右 （默认）
    end：从右到左
    center：居中
    between：两边不留空间， 剩余空间间隔平分
    around：两边留空间， 间隔空间的一半
```
```
cross：交叉轴对齐方式  align-items （单行的时候，wrap:nowrap生效）
     start：从上到下
     end：从下到上
     center：居中
     baseline：跟随内容高度对齐
     stretch：高度铺满         （默认）
```

```
row：交叉轴多行对齐方式  align-content（多行的时候，wrap:start/end，内容超过一行生效）
     start：从上到下
     end：从下到上
     center：居中
     baseline：跟随内容高度对齐
     stretch：高度铺满        （默认）
```


```
box：子元素设置
    mean：子元素平分空间
    first：除了第一个元素， 其他的平分空间
    last：除了最后一个元素， 其他的平分空间
    justify：除了第一个和最后一个元素， 其他的平分空间
```

### flex-box attributes description
```
values range ( 0-10 ), how to asign spare space to individual child element: if the value equals 0,there won't
be any spare space for this child element.
spare space assignment = current value of flex-box / the sum of all values of child element's flex-box
```

