---
layout: post
title:  "Protocol extensions case"
date:   2022-06-12 09:42:56 +0200
categories: jekyll update
---

### 

{% highlight swift %}
protocol OneMethodProtocol {
    func method1()
}
extension OneMethodProtocol {
    func method1() {
        print("| method1 | OneMetodProtocol |")
    }
    func method2() {
        print("| method2 | OneMetodProtocol |")
    }
}
struct Struct: OneMethodProtocol {
    func method1() {
        print("| method1 | Struct           |")
    }
    func method2() {
        print("| method2 | Struct           |")
    }
}

let onlyStruct = Struct()
let protocoledStruct: OneMethodProtocol = Struct()

onlyStruct.method1()       // | method1 | Struct           |
onlyStruct.method2()       // | method2 | Struct           |

protocoledStruct.method1() // | method1 | Struct           |
protocoledStruct.method2() // | method2 | OneMetodProtocol |
{% endhighlight %}

{% highlight swift %}
protocol OneMetodProtocol {
    func method1(text: String)
}
extension OneMetodProtocol {
    func method1(text: String = "default") {
        print("| method1 | OneMetodProtocol | \(text) |")
    }
    func method2(text: String = "default") {
        print("| method2 | OneMetodProtocol | \(text) |")

    }
}

struct Struct: OneMetodProtocol {
    func method1(text: String = "default") {
        print("| method1 | Struct           | \(text) |")
    }
    func method2(text: String = "default") {
        print("| method2 | Struct           | \(text) |")
    }
}

let onlyStruct = Struct()
let protocoledStruct: OneMetodProtocol = Struct()

onlyStruct.method1()                      // | method1 | Struct           | default |
onlyStruct.method2()                      // | method2 | Struct           | default |

onlyStruct.method1(text: "custom ")       // | method1 | Struct           | custom  |
onlyStruct.method2(text: "custom ")       // | method2 | Struct           | custom  |

protocoledStruct.method1()                // | method1 | OneMetodProtocol | default |
protocoledStruct.method2()                // | method2 | OneMetodProtocol | default |

protocoledStruct.method1(text: "custom ") // | method1 | Struct           | custom  |
protocoledStruct.method2(text: "custom ") // | method2 | OneMetodProtocol | custom  |
{% endhighlight %}




