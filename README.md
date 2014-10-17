2014年10月17日11:50:39
1、把NWDL json 整理好了
    1、2层是每个组的最高层
    2、3层是最底层
    3、2层的话，不需要向上查找它的父集，name就是自己的name，值取default
    4、3层需要向上查找父集，取得父集的name值，值取default，在3层会有valtype:range,此时的值就是传进来的原值，不需要转换
    5、当valtype是null的时候，代表取default；当valtype是range的时候，值是原值；当valtype是group的时候，值取default且需要循环取得。
    6、后面的DWL以及比分也将采用这种方式获取。
2、如此的话，那么
    var a = []
    var c = "item-name",d = "item-content"
    var b = [c,d]
    a.push(b)
    console.log(a)
    [Array[2]]
    undefined
    console.log(a[0])
    ["item-name", "item-content"]



["联赛"]
    ["itme-name","item-content"]
    ["itme-name","item-content"]
    ["itme-name","item-content"]
["初始赔率"]
    ["item-name","item-content"]
    ["item-name","item-content"]
    ["item-name","item-content"]

(2,"self-name",value)
    .push({"self-name":value})
(3,"parent-name","self-name",value)
    temp = ["self-name",value]
    "parent-name".push(tempd)