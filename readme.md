#图片查看器 imageViewer v1.0.0
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
