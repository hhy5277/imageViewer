#图片查看器 imageViewer v1.0.0
##简介

纯javascript图片查看器，可缩放（滚轮）、旋转（中键）、平移（左键）、翻转

###模式

三种模式 -- `CSS3`、`filter`、`canvas`

###默认属性

    options = {
                mode: "css3|filter|canvas", // 默认，根据浏览器支持的情况选择合适的模式
                zoom: 0.1, // 缩放比率
                onPreLoad: function() {}, // 图片加载前执行
                onLoad: function() {}, // 图片加载后执行
                onError: function(err) {} // 出错时执行
            };

##使用
###引入
    // common.js是自己维护的一个js库，汇集了开发时常用的方法
    <script src="../dist/js/common.min.js"></script>
    <script src="../dist/js/imageViewer.min.js"></script>
###添加容器
    <div id="imageViewer"></div>
###初始化
    // $$("imageViewer")就是使用了common.js里根据id获取元素的方法
    var container = $$("imageViewer"),
        src = "img/img_1.jpg",
        options = {
            onPreLoad: function() {
                container.style.backgroundImage = "url('img/loading.gif')";
            },
            onLoad: function() {
                container.style.backgroundImage = "";
            }
        },
        iv = new imageViewer(container, options);
    iv.load(src);
