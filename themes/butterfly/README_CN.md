# hexo-theme-butterfly

<a href="https://github.com/jerryc127/hexo-theme-butterfly/releases"><img alt="Version" src="https://img.shields.io/badge/release-2.2.0-blue"/></a>
<a href="https://jerryc.me"><img alt="Author" src="https://img.shields.io/badge/author-JerryC-blur"/></a>
<a href="https://hexo.io"><img alt="Hexo" src="https://img.shields.io/badge/hexo-4.0+-0e83c"/></a>
<a href="https://nodejs.org/"><img alt="node.js" src="https://img.shields.io/badge/node.js-8.0+-blur"/></a>

Demo:  https://demo.jerryc.me/ 

JerryC:  https://jerryc.me/


一款基於[hexo-theme-melody](https://github.com/Molunerfinn/hexo-theme-melody)修改的主題

## 安裝

在你的博客根目錄裡

```
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
```

如果想要安裝比較新的dev分支，可以

```
git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly
```

## 應用主題
修改hexo配置文件`_config.yml`，把主題改為`Butterfly`

```
theme: Butterfly
```

>如果你沒有pug以及stylus的渲染器，請下載安裝： npm install hexo-renderer-pug hexo-renderer-stylus --save or yarn add hexo-renderer-pug hexo-renderer-stylus

## 平滑升級
為了主題的平滑升級, Butterfly 使用了 data files特性。
推薦把主題默認的配置文件_config.yml複製到 Hexo 工作目錄下的source/_data/butterfly.yml，如果source/_data的目錄不存在那就創建一個。


## 文檔

可查看[hexo-theme-butterfly docs](https://docs.jerryc.me) 和 [JerryC](https://jerryc.me/posts/21cfbf15)

## 截圖
![image](https://user-images.githubusercontent.com/16351105/58887365-1272f780-8718-11e9-9329-3292c6ba20d4.png)
![image](https://user-images.githubusercontent.com/16351105/58887457-3cc4b500-8718-11e9-9417-2bdea603c92e.png)

![](https://user-images.githubusercontent.com/16351105/69338594-7d03f980-0c9e-11ea-8b64-7f165e6508e2.png)




## 標籤外掛（Tag Plugins）
> 標籤外掛是Hexo獨有的功能，並不是標準的Markdown格式。以下的寫法，只適用於Butterfly主題，用在其它主題上不會有效果，甚至可能會報錯。使用前請留意

### Note (Bootstrap Callout)
移植於next主題

#### 配置
配置butterfly.yml
```
note:
  # Note tag style values:
  #  - simple    bs-callout old alert style. Default.
  #  - modern    bs-callout new (v2-v3) alert style.
  #  - flat      flat callout style with background, like on Mozilla or StackOverflow.
  #  - disabled  disable all CSS styles import of note tag.
  style: simple
  icons: false
  border_radius: 3
  # Offset lighter of background in % for modern and flat styles (modern: -12 | 12; flat: -18 | 6).
  # Offset also applied to label tag variables. This option can work with disabled note tag.
  light_bg_offset: 0
```
#### 用法
```
{% note [class] [no-icon] %}
Any content (support inline tags too.io).
{% endnote %}

[class]   : default | primary | success | info | warning | danger.
[no-icon] : Disable icon in note.

All parameters are optional.
```

#### 例如：
```
{% note default %}
default 提示塊標籤
{% endnote %}

{% note primary no-icon %}
primary 提示塊標籤
{% endnote %}

{% note success %}
success 提示塊標籤
{% endnote %}

{% note info %}
info 提示塊標籤
{% endnote %}

{% note warning %}
warning 提示塊標籤
{% endnote %}

{% note danger %}
danger 提示塊標籤
{% endnote %}
```

> style: simple  

![image](https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/20200105232825.png)

> modern

![image](https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/20200105233018.png)

> style: flat

![image](https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/20200105233145.png)

> style: disabled

![image](https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/20200105233310.png)

### Gallery相冊圖庫
2.2.0以上提供，一個圖庫集合。

寫法
```
<div class="gallery-group-main">
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
</div>
``` 
- name：圖庫名字
- description：圖庫描述
- link：連接到對應相冊的地址
- img-url：圖庫封面的地址

例如：
```
<div class="gallery-group-main">
{% galleryGroup '壁紙' '收藏的一些壁紙' '/Gallery/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
{% galleryGroup '漫威' '關於漫威的圖片' '/Gallery/marvel' https://i.loli.net/2019/12/25/8t97aVlp4hgyBGu.jpg %}
{% galleryGroup 'OH MY GIRL' '關於OH MY GIRL的圖片' '/Gallery/ohmygirl' https://i.loli.net/2019/12/25/hOqbQ3BIwa6KWpo.jpg %}
</div>
```

### Gallery相冊
2.0.0以上提供。區別於舊版的Gallery相冊, 新的Gallery相冊會自動根據圖片長度進行排版，書寫也更加方便，與markdown格式一樣。可根據需要插入到相應的md。

寫法:
```
{% gallery %}
markdown 圖片格式
{% endgallery %}
```

例如
```
{% gallery %}
![](https://gratisography.com/wp-content/uploads/2019/10/gratisography-scary-pumpkin-hand-900x600.jpg)
![](https://gratisography.com/wp-content/uploads/2019/10/gratisography-fresh-fish-dinner-900x600.jpg)
![](https://gratisography.com/wp-content/uploads/2019/10/gratisography-mountain-cloud-landscape-900x600.jpg)
![](https://picjumbo.com/wp-content/uploads/iphone-free-stock-photos-2210x3315.jpg)
![](https://picjumbo.com/wp-content/uploads/young-millennial-girl-drinking-lemonade-and-overlooking-the-city-2210x1473.jpg)
![](https://picjumbo.com/wp-content/uploads/modern-graphic-designer-essentials_free_stock_photos_picjumbo_HNCK4919-2210x1474.jpg)
{% endgallery %}
```

### tag-hide
2.2.0以上提供。如果你想把一些文字、內容隱藏起來，並提供按鈕讓用户點擊顯示。可以使用這個標籤外掛。

寫法：
> inline 在文本里面添加按鈕隱藏內容，只限文字( content不能包含當引號，可用&apos;)

```
{% hideInline content,display,bg,color %}
```
- content: 文本內容
- display: 按鈕顯示的文字(可選)
- bg: 按鈕的背景顏色(可選)
- color: 按鈕文字的顏色(可選)
- block獨立的block隱藏內容，可以隱藏很多內容，包括圖片，代碼塊等等

```
{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```
- content: 文本內容
- display: 按鈕顯示的文字(可選)
- bg: 按鈕的背景顏色(可選)
- color: 按鈕文字的顏色(可選)

例如：

inline
```
哪個英文字母最酷？ {% hideInline 因為西裝褲(C裝酷),查看答案,#FF7242,#fff %}

門裏站着一個人? {% hideInline 閃 %}
```

block
```
{% hideBlock 查看答案 %}
{% gallery %}
![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
{% endgallery %}
{% endhideBlock %}
```

### mermaid
使用mermaid標籤可以繪製Flowchart（流程圖）、Sequence diagram（時序圖 ）、Class Diagram（類別圖）、State Diagram（狀態圖）、Gantt（甘特圖）和Pie Chart（圓形圖），具體可以查看mermaid文檔

寫法：
```
{% mermaid %}
內容
{% endmermaid %}
```

例如：
```
{% mermaid %}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
{% endmermaid %}
```