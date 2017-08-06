# Slider+
仿小红书iOS App图片自适应

目前还未封装完成~


制作思路与实现方式

1) 卡的原因与解决办法
  1. 操作的dom太长 （动态计算下一张/上一张图片，进行拼凑）
  2. 重绘/回流太多 (将滚动元素position: absolute出来，底下的元素用transform处理)
  3. requestAnimationFrame刷新频率低 （改用setTimeout处理，牺牲部分速度换流畅度）

2) 实现方式
  1. 初始化加载所有图片，计算所有图片的位置
  2. 不用canvas，用dom+img
  3. touchend时进行prev/next元素的拼凑
  4. 操作的时候始终只处理3个dom (prev/now/next)
  5. 底下的内容元素使用transform处理

