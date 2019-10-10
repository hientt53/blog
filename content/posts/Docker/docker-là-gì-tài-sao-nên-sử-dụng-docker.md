+++
categories = ["devops"]
date = "2019-10-09T17:00:00+00:00"
tags = ["become-a-devops", "docker"]
title = "Docker là gì và vì sao sử dụng docker."

+++
Để trả lời cho cầu hỏi  vì sao sử dụng docker, chúng ta hãy xem cách thông thường chúng ta cài đặt 1 phần mềm dưới đây: .

1. Tải bản cài đặt.
2. Chạy file cài đặt.
3. Gặp lỗi khi cài đặt.
4. Khắc phục lỗi.
5. Chạy lại cài đặt.
6. Nhận được lỗi khác -> quay lại bước 4.

Để  cũ thể chúng ta hãy xem cách các đặt redis được hướng dẫn trên trang chủ như sau: 

    wget http://download.redis.io/redis-stable.tar.gz
    tar xvzf redis-stable.tar.gz
    cd redis-stable
    make

Khi lệnh `wget ``[http://download.redis.io/redis-stable.tar.gz](http://download.redis.io/redis-stable.tar.gz "http://download.redis.io/redis-stable.tar.gz")`

máy báo thiếu không tìm thấy lênh `wget`, vậy là lỗi ngay từ bước 1, để tiếp tục chúng ta sẽ đi cài wget bằng lệnh `apt install wget` sau đó chạy lại lệnh `wget ``[http://download.redis.io/redis-stable.tar.gz](http://download.redis.io/redis-stable.tar.gz "http://download.redis.io/redis-stable.tar.gz")` lần này mọi việc đã thuận lợi hơn, chúng ta chuyển tiếp qua bước 3,4..