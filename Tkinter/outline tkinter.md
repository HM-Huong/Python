# Outline tkinter

## Tạo một ứng dụng GUI đơn giản sử dụng tkinter trong Python

### GUI là gì?

### Giới thiệu về tkinter

### Tạo một cửa sổ đơn giản

- Title
- Size
- Position
- Màu nền

### Tạo một label

- Hàm `Label()`
- Các thuộc tính của label
	- text
	- image
		- `PhotoImage(image="path/to/image")`: tạo một đối tượng ảnh
	- font
- Phương thức `pack()`

---

## Dàn layout

### Giới thiệu về frame

### Tạo một frame

- Hàm `Frame(parent, options)`
	- `parent`: đối tượng cha của frame
	- `options`: các thuộc tính của frame
		- `width`
		- `height`
		- `bg`: màu nền
- Phương thức `grid()`
	- `row`: chỉ số hàng
	- `column`: chỉ số cột
	- `padx`: padding. Khoảng cách giữa widget và widget = padding widget 1 + padding widget 2
	- `pady`
	- `ipadx`: internal padding
	- `ipady`: internal padding

### Chèn một frame hoặc một widget vào frame khác

Hướng dẫn học sinh tạo dàn layout có dạng như sau:

![layout](attachments/Pasted%20image%2020231106155614.png)

---

## Tạo một button

- `Button`
	- `text`
	- `command`: hàm được gọi khi button được nhấn
		- `root.quit()`: đóng cửa sổ `root`
	- `state`: trạng thái của button
		- `NORMAL`: button có thể nhấn được (mặc định)
		- `DISABLED`: button không thể nhấn được
	- `image`

Tạo một ứng dụng điều khiển đơn giản sử dụng button
![remote](attachments/Pasted%20image%2020231106161739.png)

### Đoán số

<https://www.youtube.com/watch?v=3CKSo-2fStM>

---

## Layout manager

- Giới thiệu về layout manager

### Pack layout manager

Làm cho các widget được xếp liên tiếp nhau theo hàng ngang hoặc hàng dọc.

#### Một vài tham số được sử dụng trong phương thức pack()

Compute a rectangular area called a parcel that’s just tall (or wide) enough to hold the widget and fills the remaining width (or height) in the window with blank space.
Center the widget in the parcel unless a different location is specified.

- `side`: vị trí của widget trong cửa sổ
	- `LEFT`
	- `RIGHT`
	- `TOP` (mặc định)
	- `BOTTOM`
- `fill`: lấp đầy widget trong widget cha
	- `X`: lấp đầy chiều ngang
	- `Y`: lấp đầy chiều dọc
	- `BOTH`: lấp đầy cả chiều ngang và chiều dọc
- `padx`, `pady`: khoảng cách giữa xung quanh widget
- `ipadx`, `ipady`: padding bên trong widget
- `expand`: nếu có giá trị là `True` thì widget sẽ được co dãn ra khi cửa sổ thay đổi kích thước. Mặc định là `False`
- `anchor`: vị trí của widget trong widget cha
	- `N`: trên cùng
	- `S`: dưới cùng
	- `E`: bên phải
	- `W`: bên trái
	- `NE`: trên cùng bên phải
	- `NW`: trên cùng bên trái
	- `SE`: dưới cùng bên phải
	- `SW`: dưới cùng bên trái
	- `CENTER`: giữa (mặc định)

#### làm một form đăng nhập

- Giới thiệu về `Entry`
	- `show`: thay thế ký tự nhập vào bằng ký tự khác
- Giới thiệu về `Checkbutton`

![login page](attachments/Pasted%20image%2020231106165651.png)

### Grid layout manager

#### Một vài tham số được sử dụng trong phương thức grid()

- `row`, `column`: chỉ số hàng và cột
- `rowspan`, `columnspan`: số hàng và cột mà widget chiếm
- `padx`, `pady`: khoảng cách giữa xung quanh widget
- `ipadx`, `ipady`: padding bên trong widget
- `sticky`: vị trí của widget trong widget cha
	- `N`: trên cùng
	- `S`: dưới cùng
	- `E`: bên phải
	- `W`: bên trái
	- `NE`, `NW`, `SE`, `SW`: các góc
	- `W+E+N+S`: lấp đầy (các) ô

[Tic Tac Toe Game](https://www.youtube.com/watch?v=xx0qmpuA-vM)

#### Làm một form đơn giản về thông tin cá nhân

- Cách xử lý nhiều `Checkbutton` được chọn (ví dụ: ngôn ngữ lập trình yêu thích)

### Place layout manager

#### Một vài tham số được sử dụng trong phương thức place()

- `in_`: widget cha
- `x`, `y`: tọa độ của widget trong widget cha, tính từ góc trên bên trái
- `relx`, `rely`: vị trí của widget trong widget cha dưới dạng phần trăm. Giá trị từ 0 đến 1
- `relwidth`, `relheight`: chiều rộng và chiều cao của widget dưới dạng phần trăm so với widget cha. Giá trị từ 0 đến 1
- `anchor`: tọa độ gắn với widget (x, y được tính từ tọa độ này)
	- `N`: trên cùng
	- `S`: dưới cùng
	- `E`: bên phải
	- `W`: bên trái
	- `NE`: trên cùng bên phải
	- `NW`: trên cùng bên trái
	- `SE`: dưới cùng bên phải
	- `SW`: dưới cùng bên trái
	- `CENTER`: giữa (mặc định)

#### Nhược điểm của place layout manager so với grid và pack

Note that if you run this code on a different operating system that uses different font sizes and styles, then the second label might become partially obscured by the window’s edge. That’s why .place() isn’t used often. In addition to this, it has two main drawbacks:

Layout can be difficult to manage with .place(). This is especially true if your application has lots of widgets.
Layouts created with .place() aren’t responsive. They don’t change as the window is resized.
One of the main challenges of cross-platform GUI development is making layouts that look good no matter which platform they’re viewed on, and .place() is a poor choice for making responsive and cross-platform layouts.

---

### Một số widget khác

- `Radiobutton`
- `Listbox`
- `Combobox`
- ...

## Event

### Giới thiệu về event

### `window.mainloop()`

### Phương thức `.bind()`

.bind() always takes at least two arguments:

- An event that’s represented by a string of the form "\<event_name\>", where event_name can be any of Tkinter’s events
- An event handler that’s the name of the function to be called whenever the event occurs

The event handler is bound to the widget on which .bind() is called. When the event handler is called, the event object is passed to the event handler function.

---

### Projects cuối khóa

- [Sliding Puzzle Game](https://www.youtube.com/watch?v=vzzEP_YI424)
- [2048](https://www.youtube.com/watch?v=b4XP2IcI-Bg&t=139s)
- ...

# Tài liệu tham khảo

- <https://www.pythonguis.com/tutorials/create-gui-tkinter/>
- <https://realpython.com/python-gui-tkinter/#using-events-and-event-handlers>
- <https://www.pythontutorial.net/tkinter/tkinter-event-binding/>
