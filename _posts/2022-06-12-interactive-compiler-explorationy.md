---
layout: post
title:  "Compiler Explorer"
date:   2022-06-12 09:42:56 +0200
categories: jekyll update
---
# [Compiler Explorer](https://github.com/compiler-explorer/compiler-explorer)

**Compiler Explorer** is an interactive compiler exploration website. Edit code in C, C++, C#, F#, Rust, Go, D, Haskell, Swift, Pascal, [ispc](https://ispc.github.io/), Python, Java or in any of the other
[30+ supported languages](https://godbolt.org/api/languages), and see how that code looks after being compiled in real
time. Multiple compilers are supported for each language, many different tools and visualisations are available, and the
UI layout is configurable (thanks to [GoldenLayout](https://www.golden-layout.com/)).

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

