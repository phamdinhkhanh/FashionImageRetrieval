# 1. Cấu trúc dữ liệu

Chúng ta sẽ chia folder thành 3 phần, 1 phần cho train, 1 phần cho test và 1 phần cho validation.
Tập train chiếm 80%, tập test 10% và tập validation 10%.
Cách thức chia sao cho tỷ lệ train/validation/test là bằng nhau giữa các category (và cùng bằng 80:10:10).


# 2. Các files cần chuẩn bị

* dictionary.txt lưu giữ index của các category:
VD: Model của chúng ta có 3 nhãn: tshirt, trouser, boot. Khi đó các dòng của file dictionary.txt sẽ là:

tshirt 0
trouser 1
boot 2

Tuân theo cấu trúc mỗi dòng: category_name, category_index

* list_image_cate.txt xác định địa chỉ folder link tới hình ảnh và category:

cấu trúc: `image_link category_index`
Trong đó:
- image_link là link folder tới hình ảnh.
- category_index là mã index của category tương ứng ở file dictionary.txt

VD: 

./trouser/0001.jpg 1
...
./boot/0002.jpg 2

* train_test_val.txt xác định tập train/validation/test có cấu trúc như sau:

Cấu trúc: `image_link, train_type`

VD:

./trouser/0001.jpg train
./trouser/0001.jpg test
...
./boot/0002.jpg validation


Trong đó:
- image_link là link folder tới hình ảnh
- train_type: mỗi hình ảnh có 1 train_type rơi vào 1 trong 3 giá trị {'train', 'val', 'test'} để đánh dấu hình ảnh đó thuộc về tập số liệu train/validation hay test.

# 3. Giải nén folder:

extract folder `train.zip` vào folder train.

