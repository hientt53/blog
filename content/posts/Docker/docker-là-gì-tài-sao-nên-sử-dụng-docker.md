+++
categories = ["devops"]
date = "2019-10-09T17:00:00+00:00"
tags = ["become-a-devops", "docker"]
title = "Docker là gì và vì sao người người nhà nhà lại sử dụng docker - Phần 1"

+++
Trước khi

Cách 1:  Cách thông thường ( theo tài liệu từ trang chủ của redis) các bước theo thứ tự sau:

    wget http://download.redis.io/redis-stable.tar.gz
    tar xvzf redis-stable.tar.gz
    cd redis-stable
    make 

Khi mình chạy lệnh đầu tiên:

     wget http://download.redis.io/redis-stable.tar.gz

rật tiếc có lỗi xảy ra, và mình nhận đông thông báo lỗi `wget command not found`, ồ vậy là `wget` command chưa được cài đặt, chúng ta sẽ tiến hành cài đặt `wget` bằng lệnh

    apt install wget

Sau khi cài thành công `wget` chúng ta sẽ chạy lại lệnh ở bước 1 trong hướng dẫn cài redis:

     wget http://download.redis.io/redis-stable.tar.gz

lần này lệnh chạy thành công và chúng ta thực hiện tiếp lệnh 2,3,4 theo hướng dẫn và có được redis trên máy chủ.  
Vậy vấn đề ở đây là gì? Như chúng ta đã thấy ở trên, để cài được `redis` chúng ta cần cài `wget` ( phần mềm phụ thuộc). Với những ứng dụng lớn, phần mệt phụ thuộc sẽ lớn theo, khi cài đặt chúng ta không biết trước danh sách phụ thuộc đó, và việc cài đặt ứng dụng sẽ theo quy trình sau:

1. Tải bản cài đặt.
2. Chạy file cài đặt.
3. Gặp lỗi khi cài đặt.
4. Khắc phục lỗi.
5. Chạy lại cài đặt.
6. Nhận được lỗi khác -> quay lại bước 4 cho đến khi ko còn lỗi và cài được phần mềm.  
   Thật phức tạp.

   Ủa, tại sao phức tập vậy mà không ai tìm ra cách nào đó đơn giản hơn? Tất nhiên rồi, sức mạnh của con người là vô biên mà, và con người đã tạo ra docker. Hãy xem cách chúng ta cài redis với docker.

   Cách 2: cài redis với docker.

   Để cài được redis bằng công cụ docker chúng ta chạy lệnh sau trên terminal:

       docker run -it redis 

   Bước tiếp theo là tận hưởng thành quả, redis đã được cài thành công. Docker thật vi diệu phải không a :D

[https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Untitled%20Diagram.drawio#RjZLBTsMwDIafJsdKTQNoXFcGSGgIqYchbqExTaakqbKUtjw9KXXaVdMkpBycz45j%2FzZhuemfHG%2Fk3grQJEtFT9gDyTJ6k2VkPKkYJrJhbAKVUwKDFlCoH0CYIm2VgNMq0FurvWrWsLR1DaVfMe6c7dZhX1avf214BRegKLm%2BpAclvMQubtOFP4OqZPyZpugxPAYjOEkubHeG2I6w3FnrJ8v0OehRvKjL9O7xincuzEHt%2F%2FPgPnn92Hya7eEleT%2B%2BHVVr9jzBLN9ct9gwFuuHqICzbS1gTJIStu2k8lA0vBy9XZh5YNIbHW40mJgOnIf%2Bap107j6sDVgD3g0hBB8whoLhxtB47xb9aRRVnml%2Fh4zjyKs59aJKMFCYeF0G8Oc7W2O2%2BwU%3D](https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Untitled%20Diagram.drawio#RjZLBTsMwDIafJsdKTQNoXFcGSGgIqYchbqExTaakqbKUtjw9KXXaVdMkpBycz45j%2FzZhuemfHG%2Fk3grQJEtFT9gDyTJ6k2VkPKkYJrJhbAKVUwKDFlCoH0CYIm2VgNMq0FurvWrWsLR1DaVfMe6c7dZhX1avf214BRegKLm%2BpAclvMQubtOFP4OqZPyZpugxPAYjOEkubHeG2I6w3FnrJ8v0OehRvKjL9O7xincuzEHt%2F%2FPgPnn92Hya7eEleT%2B%2BHVVr9jzBLN9ct9gwFuuHqICzbS1gTJIStu2k8lA0vBy9XZh5YNIbHW40mJgOnIf%2Bap107j6sDVgD3g0hBB8whoLhxtB47xb9aRRVnml%2Fh4zjyKs59aJKMFCYeF0G8Oc7W2O2%2BwU%3D "https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Untitled%20Diagram.drawio#RjZLBTsMwDIafJsdKTQNoXFcGSGgIqYchbqExTaakqbKUtjw9KXXaVdMkpBycz45j%2FzZhuemfHG%2Fk3grQJEtFT9gDyTJ6k2VkPKkYJrJhbAKVUwKDFlCoH0CYIm2VgNMq0FurvWrWsLR1DaVfMe6c7dZhX1avf214BRegKLm%2BpAclvMQubtOFP4OqZPyZpugxPAYjOEkubHeG2I6w3FnrJ8v0OehRvKjL9O7xincuzEHt%2F%2FPgPnn92Hya7eEleT%2B%2BHVVr9jzBLN9ct9gwFuuHqICzbS1gTJIStu2k8lA0vBy9XZh5YNIbHW40mJgOnIf%2Bap107j6sDVgD3g0hBB8whoLhxtB47xb9aRRVnml%2Fh4zjyKs59aJKMFCYeF0G8Oc7W2O2%2BwU%3D")