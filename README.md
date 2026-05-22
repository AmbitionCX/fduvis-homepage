# FDUVIS网站管理文档
- 开发和部署方式： `hexo` + `github pages`
- Hexo 使用方法：https://hexo.io/zh-cn/docs/
- 模板名称： `micall`
- 调试：输入 `hexo server`，就可以在 `http://localhost:4000/` 开始调试
- 更新：分别输入：
    - hexo clean（清除缓存）
    - hexo generate（生成）
    - hexo deploy（部署）

## 重要文件：
- 模板作者撰写的 `README` 文档：`themes\micall\readme.md` 包含部分目录、文件功能的描述，当需要重构网站时可以参考。
- 主要信息配置文件： `themes\micall\_config.yml` 
> **重要！** 用于设置首页上的欢迎词、介绍词等，也用于登记导航栏中的子页面。

## 图片存放地址：
- 图片都存放在此目录下的文件夹里： `themes\micall\source`
- 主页合照、微信二维码： `images`
- Logo、背景图： `img`
- 成员照片： `members`（除导师外需裁剪为正方形以正常显示）
- 论文发表预览图： `publications`
- 获奖预览图： `awards`
- 新闻图片： `news`
- 实验室相册： `photos`
- 建议所有图片进行压缩后再上传，可使用 [iloveimg](https://www.iloveimg.com/) 进行裁剪，使用 [tinypng](https://tinify.com/web) 进行压缩。

Compress PNG images
```shell
# quality: 1 (worst quality, smallest file) - 100 (best quality, largest file):
convert input.png -quality 20 -strip output.jpg
```

## 信息存放地址：
- 各类信息表存放在此目录下： `source\_data`
- 指导老师： `director.yml`
- 博后与研究助理：`administrators.yml`
- 博士生： `phds.yml`
- 研究生： `masters.yml`
- 本科生： `undergraduates.yml`
- 访问学生： `visiting.yml`
- 毕业生：`graduated.yml`
- 获奖： `awards.yml`
- 论文发表： `publications.yml`
- 新闻： `news.yml`
- 相册： `gallery.yml`
- 当需要更新信息时（如添加成员、新闻），按照原格式在文件最上方继续添加即可。

## 研究方向标签：
主要用于对发表论文进行分类归档，在 `publications.yml` 中添加新论文时，使用project字段为论文增加分类标签，对应如下：
- AI4VIS： `ai4vis`
- Explainable AI： `explainable_ai`
- 社交模拟仿真： `social_simulation`
- 自动驾驶： `autonomous_driving`
- 生物智能： `bio_intelligence`
- 数字人文： `digital_humanities`
- 智能教育： `smart_education`
- 智能电力： `smart_power`
- 金融科技： `financial_technology`
- 文化智能： `culture_intelligence`
- 三维可视化： `three_d_viz`
- 故事叙述： `storytelling`
- Intelligent VA： `intelligent_va`
- UI Agent： `ui_agent`

## 页面源代码：
页面代码保存在此目录下： `themes\micall\layout`
- `_widget` 文件夹：子页面源代码都在此文件夹下，如发表论文页、成员页、各个研究方向的子页面等
- 在导航栏添加新页面的步骤（由于使用的模板较为古旧，步骤比较繁琐）：
1. 在配置文件 `themes\micall\_config.yml` 中的 `pages` 字段下登记新页面
2. 在 `source` 文件夹下新建文件夹，然后和其它文件夹下一样（如对应新闻的 `news` 文件夹），添加一个 `index.md` 文件（需要改内部字段，不要直接复制）
3. 在 `themes\micall\layout\post.ejs` 文件中添加新页面的链接
4. 在 `themes\micall\layout\_widget` 文件夹下编写新页面的具体代码