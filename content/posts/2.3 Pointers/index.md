---
title: "2.3 Pointers"
date: 2019-04-01T11:00:22+07:00
draft: false
---



```go
    type user struct {
        name string
        email string
    }

    func main(){
        u1 := createuserV1()
        u2 := createuserV2()

        fmt.Println("u1", &u1, "u2", &u2)
    }

    // createUserV1 creates a user value and passed 
    // a copy back to the caller.
    //go:noinline
    func createuserV1() user {
        u := user{
            name: "Bill",
            email: "bill@ardanlabs.com",
        }

        fmt.Println("V1", &u)

        return u
    }

    func createuserV2() *user {
        u := user{
            name: "Bill",
            email: "bill@ardanlabs.com",
        }

        fmt.Println("V@", &u)

        return &u
    }
```

{{< figure src="v1.jpg" caption="create user 1 on frame"
>}}

{{< figure src="v2.jpg" caption="create user 2 on frame"
>}}

**Ghi chú 1**: Ở createuserV2 `return &u`, nhìn vào `&u`  nhận thấy trả về pointer -> phải dùng bộ nhớ heap -> tăng cost 

**Ghi chú 2:** Không construction với pointer ví dụ: 

```go
    u := &use
        name: "Bill",
        email: "bill@ardanlabs.com",
    }

    fmt.Println("V1", u)

    return u
```

khi đọc code vd:  `return u` ta không thể biết `U` là pointer hay không. ( Có thể khi return ngay lập tức, hoặc dùng làm tham số cho 1 function)