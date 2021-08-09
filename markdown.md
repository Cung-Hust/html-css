Giới thiệu
Keyword: CSS selectors

Trong CSS, CSS selectors là các cách chúng ta sử dụng để chọn ra các phần tử (elements) mà chúng ta muốn “style” cho chúng.

Chú ý: Thẻ có cách nói khác là Tag, khi các thẻ được trình duyệt “đọc” và render ra giao diện website thì có thể gọi các thẻ là các “phần tử” hay các “elements”.

CSS selectors cơ bản
Trong bài này mình chỉ đưa ra những CSS selectors cơ bản và thường xuyên được sử dụng nhất.

Selector Ví dụ Mô tả
.class .intro Chọn tất cả các thẻ có class=“intro”
.class1.class2 .name1.name2 Chọn tất cả các thẻ có cả name1 và name2 được đặt trong thuộc tính class của nó
.class1 .class2 .name1 .name2 Chọn tất cả các thẻ có class=“name2” là con của một phần tử có class=“name1”

- - Chọn tất cả các thẻ
    element h2 Chọn tất cả các thẻ h2
    element.class div.box Chọn tất cả thẻ div có class=“box”
    element, element div, h2 Chọn tất cả thẻ div và h2
    element element div p Chọn tất cả thẻ p trong thẻ div
    element > element div > p Chọn tất cả thẻ p là con trực tiếp của thẻ div
    element + element div + p Chọn thẻ p đứng liền kề sau thẻ div
    element ~ element div ~ p Chọn tất cả thẻ p đứng sau thẻ div
    Tham khảo thêm tại: https://www.w3schools.com/cssref/css_selectors.asp

CSS selectors là công cụ vô cùng mạnh mẽ. Toàn bộ các selectors trong CSS đều có thể linh động kết hợp với nhau khi sử dụng giúp lập trình viên có thể chọn được bất cứ phần tử HTML nào trong website.

Một số ví dụ sử dụng CSS selectors
Ví dụ 0:
Để chọn toàn bộ tất cả các thẻ HTML chúng ta có thể sử dụng selector \*. Trường hợp phổ biến nhất sử dụng selector này là khi reset CSS (loại bỏ các thuộc tính margin và padding mặc định của các thẻ HTML.

- {
  padding: 0;
  margin: 0;
  }
  Như đoạn mã CSS trên thì toàn bộ các thẻ HTML đều có padding và margin bằng 0. Mặc định thì một số thẻ như h1-h6, p, ul, ol, … sẽ có padding hoặc margin mặc định gây ra những sai lệch trong giao diện ngoài ý muốn của LTV.

Nên việc đưa padding và margin về 0 thường được gọi là Reset CSS.

Reset CSS là công việc chúng ta thường làm ngay từ khi bắt đầu xây dựng một trang web.

Sau này khi muốn một thẻ nào đó trong website có padding hoặc margin chúng ta chỉ cần đặt class và CSS cho thẻ đó như bình thường. Thuộc tính được CSS qua selector \* sẽ có độ ưu tiên thấp hơn các selectors khác.

Ví dụ 1:
Chọn các thẻ p

<style>
    p {
        color: 
red;
    }
</style>

<h1>Heading 1</h1>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
Ví dụ 2:
Chọn các thẻ có class paragraph1

<style>
    .paragraph1 {
        color: 
red;
    }
</style>
<h1>Heading 1</h1>
<p class="paragraph1">Paragraph 1</p>
<p class="paragraph1">Paragraph 1</p>
<p>Paragraph 2</p>
Ví dụ 3:
Chọn các thẻ có class paragraph và class p1

<style>
    .paragraph.p1 {
        color: 
red;
    }
</style>
<h1>Heading 1</h1>
<p class="paragraph p1">Paragraph 1</p>
<p class="paragraph p1">Paragraph 1</p>
<p class="paragraph">Paragraph 2</p>
Ví dụ 4:
Chọn các thẻ có class children là con của thẻ có class parent

<style>
    .parent .children {
        color: 
red;
    }
</style>

<!-- Trường hợp .children là con trực tiếp của .parent -->
<div class="parent">
    <div class="children">Children 1</div>
    <div class="children">Children 2</div>
    <div class="children">Children 3</div>
</div>

<!-- Hoặc các .children nằm rải rác, miễn là con của .parent -->
<div class="parent">
    <div class="children">Children 1</div>

    <div class="other-div">
        <div class="children">Children 2</div>

        <div class="other-div">
            <div class="children">Children 3</div>
        </div>
    </div>

</div>
Để xem các ví dụ trực quan hơn các bạn hãy tham khảo qua công cụ “CSS selectors tester” rất trực quan, được xây dựng bởi w3school tại đây: https://www.w3schools.com/cssref/trysel.asp
