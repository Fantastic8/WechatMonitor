# WechatMonitor
微信投票实时监控

简介：
这个脚本主要用于监控微信投票是否存在刷票情况，运行脚本后可以看到页面上会增加一个动态折线图，以及以截图频率为周期依次添加到末尾的屏幕截图和统计表格。因为屏幕截图会消耗一定时间，所以统计表格与屏幕截图之间可能会有时间差，但数据是真实的。
脚本运行需要Chrome浏览器，其他浏览器能否运行未知。
监控期间需要一直开启浏览器，任何断网，关闭浏览器都会造成数据全部丢失。所以请定时保存网页。（右击打印，另存为pdf；不能使用另存为网页）



使用步骤：
1. 使用Chrome浏览器打开http://mp.yidaweixin.com/
2. 将想要进行监控的投票网页（微信投票）复制到该输入框中并点击提交监控，页面跳转后即可看到网页正在进行实时监控，但不能给出具体什么时间，谁增长了多少票。
3. 按F12浏览器会弹出开发者窗口
4. 找到弹出窗口中的"Sources"选项卡并点击
5. 进入选项卡后又有一行小选项卡，找到"Snippets",并点击。
6. 右击旁边的空白区域，选择"New"或"New Snippets"创建新文件（文件名无所谓）
7. 创建好文件后将Monitor.js文件里面的所有代码复制进去
8. 按住Crtl+Enter运行代码
9. 再次按F12窗口关闭，让代码好在后台运行。

注意事项：
1. 代码运行后必须要一直开启这个网页，任何一次关闭网页都会造成数据丢失，并重新记录。
2. 在空白处右击打印，可以将网页存成pdf文件到本地。
3. 目前只试验过Chrome浏览器，其他浏览器能否运行未知。
4. 修改参数在Monitor.js文件开头会有三个可变参数：
    (1): diagram_frequence是指定折线图的刷新频率，以秒为单位；默认为60秒刷新一次，折线图第一次刷新会在指定的刷新频率后才出现。
    (2): capture_frequence是指截图频率，以秒为单位；默认为30分钟刷新一次。
    (3): dataLength是指折线图显示数据点个数，默认为不限制，若想限制个数需要将7440-7442行的代码取消注释。
