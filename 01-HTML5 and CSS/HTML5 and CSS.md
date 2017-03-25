- #### link to Google font

  - if a font doesn't available

- #### img 

  - ```html
    <img class="smaller-img" src="...url..." alt="如果没有加载出来如何显示">
    ```


- #### border

  - border-color
  - border-width
  - border-style
  - border-radius
    - 可以用px，也可以用百分比，50%就是整圆



- #### link

  - ```html
    <p>Here's a
      <a href='url'>link's text</a>
      for you to follow.
    </p>
    ```

  - **hash symbol** 【jQuery】**'#'**

    - ```html
      <p>Click here for <a href='#'>cat photos</a>.</p>
      ```

    - to turn it into a **dead link**

      - href="#" 指向文档头，就是会跳转到这个网页的最上面
      - 要是href="#aaa"，点击后页面就会跳到页面上id=aaa的元素上
        - 类似网页内部跳



- #### unordered lists

  - ```html
    <ul>
      <li>milk</li>
      <li>cheese</li>
    </ul>
    ```

- #### ordered lists

  - ```html
    <ol>
      <li>milk</li>
      <li>cheese</li>
    </ol>
    ```

- #### Text inputs

  - ```html
    <input type="text">
    ```

- #### placeholder text

  - what appears in your text `input` before your user has input anything.

  - ```html
    <input type="text" placeholder="this is placeholder text">
    ```

- #### web forms

  - You can build web forms that actually submit data to a server using nothing more than pure HTML. You can do this by specifying an action on your `form`element.

  - ```html
    <form action="/url-where-you-want-to-submit-form-data"></form>

    <form action="/submit-cat-photo"><input type="text" placeholder="cat photo URL"></form>
    ```

- #### submit button

  - ```html
    <form action="/submit-cat-photo">
      <input type="text" placeholder="cat photo URL">
      <button type="submit">Submit</button>
    </form>
    <!--动作的参与者都写在一个form里面，这样才会有action的发生-->
    ```

  - ```html
    <form>
      <input type="text" placeholder="url" required>
      <button type="submit">Submit</button>
    </form>
    <!--required: 就是必须要输入内容，如果未输入内容点击submit，将会出现提示：请填写此字段-->
    ```

- #### radio buttons


-   for questions where you want the user to only give you one answer.

  - All related radio button inputs should have the same `name` attribute.

  - ```html
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    ```

  - ```html
    <label>
      <input type="radio" name="indoor-outdoor">Indoor
    </label>

    <label>
      <input type="radio" name="indoor-outdoor">Outdoor
    </label>
    <!--出现的就是可以点击的小圆圈-->
    ```

  - **radio button**设置同样的name属性，说明多种选择选取时只能选上一个，不能同时被选择

- #### checkboxes


-   也是input的一种，也要nested在自己的label里面

  - All related checkbox inputs should have the same `name` attribute.

  - ```html
    <label><input type="checkbox" name="personality"> Loving</label>

    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <!--checked: 表示默认被选中-->
    <!--label: 作用是用户不一定要点击框框才会显示选中，点击文字也能设置为checked-->
    ```

  - 是方框框，可以打勾勾的

  - **checkbox**设置同样的name属性，依然能被多个选中



- #### Nest Many Elements within a Single Div Element



- #### classes & id

  - `id` attributes should be unique. 
    - 即class可以多个elements使用，但是一个id只能供一个element使用
    - 在CSS中，id是#，class是.

- #### Adjusting the Padding of an Element

  - 所有的HTML元素都是矩形

  - **padding、margin、border**

    - An element's `padding` controls the amount of space between the element and its `border`.

    - **border：边线**

      - 所有的HTML都是矩形，任何一个矩形都是有边线的，那个就是border

    - **padding：内边距**，就是自身和矩形框的距离

      - content内容到边线的距离

      - ```html
        padding-top
        padding-right
        padding-bottom
        padding-left

        <!--可以用一句话上右下左（clockwise顺时针方向）-->
        padding: 10px 20px 10px 20px;
        ```

    - **margin**

      - An element's `margin` controls the amount of space between an element's `border` and surrounding elements.

      - 距离周围元素的距离，外部距离

      - 是当前元素上下左右距离其他元素的border的距离，不是固定一个其他元素

      - 如果margin设置为负值，则这个元素会变更大

      - ```html
        margin-top
        margin-right
        margin-bottom
        margin-left

        <!--可以用一句话上右下左（clockwise顺时针方向）-->
        margin: 10px 20px 10px 20px;
        ```

- #### CSS优先级

  - `class—>id—>inline style—>!important`


-   ```html
    <style>
      body {
        background-color: black;
        font-family: Monospace;
        color: green;
      }
      .pink-text {
        color: pink;
      }
      .blue-text {
        color: blue;
      }
    </style>
    <h1 class="pink-text blue-text">Hello World!</h1>
    <!--最终h1会呈现blue，browser read CSS from top to bottom, 如果发生冲突，那么会选取CSS最后的设置来显示-->

    <style>
      body {
        background-color: black;
        font-family: Monospace;
        color: green;
      }
      #orange-text {
        color: orange;
      }
      .pink-text {
        color: pink;
      }
      .blue-text {
        color: blue;
      }
    </style>
    <h1 style="color: white" id="orange-text" class="pink-text blue-text">Hello World!</h1>
    <!--id的优先级比class更高-->
    <!--但是inline style的优先级更高-->
    ```

- #### !important

    - ```html
      <style>
        body {
          background-color: black;
          font-family: Monospace;
          color: green;
        }
        #orange-text {
          color: orange;
        }
        .pink-text {
          color: pink !important;
        }
        .blue-text {
          color: blue;
        }
      </style>
      <h1 style="color: white" id="orange-text" class="pink-text blue-text">Hello World!</h1>
      <!--id的优先级比class更高-->
      <!--但是inline style的优先级更高-->
      <!--不过如果设置了!important，则它优先级最高-->
      ```

- #### color

  - hex code 用取色器

    - `#000000`
    - **Abbreviated Hex Code**
      - 缩写十六进制代码

  - RGB

    - ```html
      rgb(0, 0, 0)
      ```

  ​