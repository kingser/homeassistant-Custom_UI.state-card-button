# 多功能按钮的自定义UI

### state-card-button.html
什么是Custom_UI? 中文翻译就是 自定义UI顾名思义,HA的原版UI局限性太大了,一行一个控制.一个空气净化器就要6/7行.太占地方.
一个灯光呢,除了开关方便,如果你要调颜色,亮度神马的,都要点开详情页才能实现,太麻烦.
所以就有了Custom_UI=自定义UI.
最早的,也是目前最常用的Custom_UI就是这个了,我们通常叫原版[Custom_UI.](https://github.com/andrey-git/home-assistant-custom-ui)
这个能实现很多功能,也有很多玩法,比如增加圆形徽章组,给灯光增加滑杆直接调亮度,显示更多的信息等...
**但是貌似忽略了一些按键功能.
然后我就针对按钮的方便性制作了一个Custom_UI.**
----------

| 作者     | Qinver |
| -------- | ------ |
| 版本     | 1.01   |
| 最后更新 |2018年06月02日 19:41:45|

## 目录
1. 支持的功能介绍
2. 安装教程
3. 配置文件
4. 注意事项

###  支持的功能
> 一句话慨阔是可以在任意一行ID中增加一些按钮,这些按钮的大小/颜色/图标/状态/功能等都可以自定义,极大的提高了扩展性

 1. 增加按钮时候可以选择本来的控制开关是否隐藏.
 2. 增加的按钮支持方块/文字/图标/自定义图片的显示
 3. 图标和背景方块的颜色支持自定义,且可以根据状态不同改变颜色
 4. 按钮的尺寸、间距、圆角半径均可自定义
 5. 可以在名称下显示附加信息.(这个和原版Custom_UI差不多)
 6. 每一个按钮可以自定义按下的动作,也是就action,和自动化的action功能一样.
>功能简单,但是玩法很多! 
#### 图片展示
 
### 安装教程
1.如果之前没有用过任何的Custom_UI！
那么:下载这个链接里面的两个文件,并放入你的配置文件目录的*==~/custom_components/customizer==*下!

完成第一步就可以使用别人制作的Custom_UI文件了
2.下载我制作的Custom_UI文件(state-card-button.html)放入你的配置目录的 *==~/www/custom_ui==* 下

3.完成以以上两步,那么就安装好了,接下来让它在HA生效
在HA配置文件中对应位置添加以下代码：

``` frontend:
  javascript_version: auto
  extra_html_url:
    - /local/custom_ui/state-card-custom-ui.html
    - /local/custom_ui/state-card-tiles.html
    - /local/custom_ui/state-card-custom-phicomm-aircat.html
    - /local/custom_ui/state-card-floorplan.html
    - /local/custom_ui/state-card-custom_light.html
    - /local/custom_ui/state-card-button.html
  extra_html_url_es5:
    - /local/custom_ui/state-card-custom-ui-es5.html
    - /local/custom_ui/state-card-tiles.html
    - /local/custom_ui/state-card-custom-phicomm-aircat.html
    - /local/custom_ui/state-card-floorplan.html
    - /local/custom_ui/state-card-custom_light.html
    - /local/custom_ui/state-card-button.html
```



## 其他

http://soft.xiaoshujiang.com/price.html

___

# 升级日志

## 注

如果您从较老版本的小书匠升级，内置数据库会有不兼容问题，建议在升级前进行数据导出备份，或者数据库文件备份，防止升级失败。

数据库文件路径

```
Windows: %LOCALAPPDATA%/storywriter/
Mac: ~/Library/Application Support/storywriter/
Linux: ~/.config/storywriter
```

# 6.0.2

## 6.0.2 修改

1. 修复绑定的第三方存储未显示文件夹，文件等图标的问题 #816

# 6.0.1

## 6.0.1 修改

1.  修复 codemirror 编辑器的任务列表bug #815

# 6.0.0

## 6.0.0 新功能

1. 添加绘图组件(drawio)功能
2. 浮动层(表格组件，涂鸦组件，绘图组件)实现最大化功能

## 6.0.0 修改

1. 升级 semanticui 到 2.3.1
2. 升级字体图标组件 fontawesome 到 5.0.12
3. 升级 mermaid 到 8.0.0 rc8 版本 #811 #803
4. 裁切图片时，图片缩放比率调整为1
5. 修改图片，保存为 jpg 时，质量保持为 1
6. 通过剪切板添加的图片能够正解处理扩展名
7. 修复导出 zip 一个 bug
8. 更方便的调整浮动窗口大小
9. 印象笔记会话过期后返回正确的错误提示
10. 修复全局语法开关修改不会被同步的 bug
11. 调整预览区单词默认间距
12. 预览区大纲正文修改后，也能实时更新
13. 修复全屏预览时，大纲按钮无效的问题
14. 修改预览区大纲在开启双向同步滚动时，定位不准确的问题 #799
15. web 版本在拍照截图时，如果跨域图片无法正常处理的问题 #809


# 5.8.0

## 5.8.0 新功能

1. 添加图片涂鸦功能（非付费用户保存时会被添加水印）
2. 实现文章拍照截图后简单涂鸦功能
3. 添加 dropbox 绑定支持绑定到默认文件夹的访问
4. 实现在 codemirror 打开超链接功能
5. 待办列表按钮
6. 脚注按钮

## 5.8.0 修改

1. 修复 codemirror 编辑区内容为 `+======`时，变成绿的小点，点击出现取色界面 #766
2. 修改语法手册里待办说明
3. 改进增强型表格语法里单元格合并算法，实现列单元格合并功能. #773
4. 标题快捷按钮操作后，自动前后空一行
5. 调整 codemirror 表格组件等自动弹出的按钮位置
6. 将 `ctrl+shift+p` 修改为打开预览

# 5.7.6

## 5.7.6 修改

1. 调整生成的块级图片 html 片段结构 [说明](https://github.com/suziwen/blogxiaoshujiang/blob/master/2018-4-25%20%E8%87%AA%E5%AE%9A%E4%B9%89%20css%20%E6%A0%B7%E5%BC%8F%E8%B0%83%E6%95%B4%E5%9D%97%E7%BA%A7%E5%9B%BE%E7%89%87%E6%A0%87%E9%A2%98%E6%98%BE%E7%A4%BA%E4%BD%8D%E7%BD%AE.md)

# 5.7.5

## 5.7.5 修改

1. 调整 zip 文件附件导入的超时时间限制 #781
2. 导入界面加入动画提示

# 5.7.4 更新

## 5.7.4 修改

1. 修复部份第三方绑定无法自动定位到文件所在目录位置的问题 #761

# 5.7.3 更新

## 5.7.3 修改

1. 代码块自动生成时，选中范围调整到整个代码区，删除多余的结尾空行 #752

# 5.7.2 更新

## 5.7.2 修改

1. 修复代码块title关键字无法正常处理带空格文字的问题 #757

# 5.7.1 更新

## 5.7.1 修改

1. 正文修改时，能及时更新大纲内容

# 5.7.0 更新

## 5.7.0 新功能

1. 大纲功能支持浮动显示 #702 #712

## 5.7.0 修改

1. 调整文章切换时鼠标焦点切换模式 #746


# 5.6.0 更新

## 5.6.0 新功能

1. 添加表格组件，[查看教程][1]
2. 添加可视化的表格编辑，表格嵌套，单元格合并等功能，[查看教程][2]（会员）
3. 实现 evernote 分组显示功能 #44 #724
4. 客户端预览窗口实现置顶开关(在左下角) #722 
5. 印象笔记在绑定设置页面里添加一个是否隐藏追加 markdown 原文的选项



## 5.1.0 到 5.5.0 之间提供的新功能

1. 多模板管理
2. 第三方存储添加支持标题查询功能 [查看使用](https://github.com/suziwen/blogxiaoshujiang/blob/master/2017-12-27%20%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AD%98%E5%82%A8%E6%9F%A5%E8%AF%A2.md)
3. 模板支持导入导出 [模板管理](https://github.com/suziwen/blogxiaoshujiang/blob/master/2017-12-30%20%E6%A8%A1%E6%9D%BF%E7%AE%A1%E7%90%86.md)
4. web 版本添加右键上下文菜单功能 （需要在编辑区或者预览区里使用 ctrl 键加鼠标右键）
5. 客户端预览区支持复制为带内联样式的 html 片段，复制为 escaped 后的 html 片段
6. 预览区右键加入选中范围字数统计功能
7. 发布功能提供是否将 svg 转换成图片选项 #693

## 5.6.0 修改

1. 合并视频，音频，附件到图片资源上传入口
2. 修复 emacs 键盘模式下部份快捷键冲突的问题 #708
3. 允许浮动层在左上角调整大小
4. url 在 markdown 文章里不再被自动编码
5. image, link 等使用行内式，而不是引用的方式
6. 七牛图床上传入口可以自定义 #728
7. mac 环境下快捷失效 #732
8. 工具栏图标大小修改

## 5.1.0 到 5.5.0 之间进行的修改

1. 添加pdf导出水印透明度支持小数提示
2. 重构模板管理页面
3. 模板提供是否支持脚本执行选项
4. 文档列表为空时，无法正常打开第三方绑定的文章 #657
5. 文件目录的标题总是换行 #659
6. 文件全部关闭时提示页面调整
7. 文件加载样式调整
8. 修复数据库导出时，文件没有及时写入，引起最后几条总是导出失败
9. 修改上下文菜单样式
10. 关于新建文件名不能及时更新的问题 #667
11. 重构输入 html 对话框功能，添加粘贴剪切板里的富文本内容
12. 阻止编辑器内的事件冒泡到外面，解决编辑器快捷键与外部快捷键的冲突, 比如(ctrl+alt+up)
13. 调整多款主题样式
14. 绑定页面数据存储去掉小书匠存储
15. 改进图片缓存策略，解决由于缓存不能正确处理 alt  title 相关属性的问题
16. 复制为 html 时，去掉小书匠系统内部使用的标签
17. 用户调整第三方存储目录排序规则时，未立即触发目录重排
18. 代码高亮时自动把 tab 转换成 space
19. 调整水印透明度
20. 修改浮动预览层大小调整图标
21. 修复 ace 编辑器里如果出现 < 符号，就会进入 html 模式的问题 #686
22. 修改 ace 编辑器内代码块的支持方式
23. 同步超时状态提示
24. 修改绑定设置窗口位置 #691 #694


  [1]: https://github.com/suziwen/blogxiaoshujiang/blob/master/2018-3-29%20%E8%A1%A8%E6%A0%BC%E7%BB%84%E4%BB%B6%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E.md
  [2]: https://github.com/suziwen/blogxiaoshujiang/blob/master/2018-3-30%20%E8%A1%A8%E6%A0%BC%E7%BB%84%E4%BB%B6%E7%BC%96%E8%BE%91%E5%99%A8%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E.md
