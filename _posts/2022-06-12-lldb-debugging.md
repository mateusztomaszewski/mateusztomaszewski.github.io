---
layout: post
title:  "LLDB debugging"
date:   2022-06-12 09:42:56 +0200
categories: jekyll update
---
# LLDB debugging

1.In LLDB, p is print and po is print object. 'p' is used to print non-pointer variables like bool, float etc. 2.'fr v bar' means show the contents of the local variable(frame variable) bar.


```
fr v -R twice_optional
```

```
fr v 
```

```
fr v -d r
```
