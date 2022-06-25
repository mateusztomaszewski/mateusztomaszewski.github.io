---
layout: post
title:  "Compiler Explorer"
date:   2022-06-12 09:42:56 +0200
categories: jekyll update
---
Have you ever wondered what the assembler code looks like in your code in Swift? I discovered a fantastic tool that allows you to do just that 🚀[Compiler Explorer](https://github.com/compiler-explorer/compiler-explorer).


### Swift example

{% highlight swift %}
func square(n: Int) -> Int {
    return n * n
}
{% endhighlight %}

{% highlight nasm %}
main:
        push    rbp
        mov     rbp, rsp
        xor     eax, eax
        pop     rbp
        ret

output.square(n: Swift.Int) -> Swift.Int:
        push    rbp
        mov     rbp, rsp
        sub     rsp, 32
        mov     qword ptr [rbp - 24], rdi
        lea     rdi, [rbp - 8]
        xor     esi, esi
        mov     edx, 8
        call    memset@PLT
        mov     rdi, qword ptr [rbp - 24]
        mov     qword ptr [rbp - 8], rdi
        imul    rdi, rdi
        mov     qword ptr [rbp - 16], rdi
        seto    al
        test    al, 1
        jne     .LBB1_2
        mov     rax, qword ptr [rbp - 16]
        add     rsp, 32
        pop     rbp
        ret
.LBB1_2:
        ud2

__swift_reflection_version:
        .short  3
{% endhighlight %}

