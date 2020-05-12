# CSS3

> CSS3 模块

CSS3被拆分为"模块"。旧规范已拆分成小块，还增加了新的。

* 一些最重要CSS3模块如下：
  * 选择器
  * 盒模型
  * 背景和边框
  * 文字特效
  * 2D/3D转换
  * 动画
  * 多列布局
  * 用户界面

> 边框

* border-radius
  * 任何元素均生效
  * 左上角，右上角，右下角，左下角
  * x / y

    ```css
      width: 200px;
      height: 200px;
      border-radius: 100% 0% 0% 0% / 100% 0% 0% 0%; // 四分之一左上圆

      width: 400px;
      height: 200px;
      border-radius: 50% 50% 0% 0% / 100% 100% 0% 0%; // 上半圆
    ```

* box-shadow
  * box-shadow: h-shadow v-shadow blur spread color inset/outset(默认值);

  ```css
    box-shadow: -20px -20px 80px 10px #000;
  ```

* border-image

> 背景

* background-image
  * 可设置多张图片，前面的图片再上，后面的图片在下
  * ` background-image: url(img_flwr.gif), url(paper.gif); `
* background-size
  * `background-size: length|percentage|cover|contain`
  * `cover|contain` 保持宽高比缩放图片
  * `background-size: 80px 60px;` // width, height
* background-origin
  * 背景图像的位置区域
  * 可为 `content-box`, `padding-box(默认值)`, 和 `border-box`
* background-clip
  * 背景绘制区域，超出绘制区域的部分留白，如剪掉了一样，但不会影响 border
  * 可为 `content-box(默认值)`, `padding-box`, 和 `border-box`

> 渐变(Gradients)

* 使两个或多个指定的颜色之间显示平稳的过渡
* 类型
  * 线性渐变(Linear Gradients)- 向下/向上/向左/向右/对角方向
  * 径向渐变(Radial Gradients)- 由它们的中心定义
* 方式
  * 线性渐变
    * `background-image: linear-gradient(direction, color-stop1, color-stop2, ...)`

      ```css
        linear-gradient(to bottom right, rgba(0,0,0,.8), rgba(255,255,255,.1)) // 左上到右下
      ```

    * `background-image: linear-gradient(angle, color-stop1, color-stop2);`

      ```css
        linear-gradient(135deg, rgba(0,0,0,.8), rgba(255,255,255,.1)) //右下到左上
        // 顺时针为正, 逆时针为负
      ```

    * `background-image: repeating-linear-gradient(red, yellow 10%, green 20%);`
      * 重复的渐变．若如上，但不重复，则剩余的 `80%` 的部分均为 `green`
  
  ```css
    width: 400px;
    height: 200px;
    background-color: #ccc;
    box-shadow: 20px 20px 80px 10px #000;
    background-image: linear-gradient(-45deg, rgba(0,0,0,.8),rgba(255,255,255,.1),rgba(0,0,0,.8));// 等价于 ...0,...50%,...100%
  ```

* 径向渐变
  * `background-image: radial-gradient(shape size at position, start-color, ..., last-color);`
    * start-color, last-color 是必需的
    * shape: circle 或 ellipse(椭圆，默认值)
    * size: closest-side(最近的边), farthest-side(最远的边), closest-corner(最近的角), farthest-corner(最远的角，默认值)

  ```css
    background-image: radial-gradient(circle, red 30%, blue 60%, yellow 100%);

    background-image: radial-gradient(closest-side at 60% 55%, red, yellow, black); // 默认的 position 是 50%, 50%(即圆心)
  ```

  * `background-image: repeating-radial-gradient(red, yellow 10%, green 15%);`
    * 重复的渐变
