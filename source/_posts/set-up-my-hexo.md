---
title: hexo 網誌建立與文章頁面建立（本地篇）
date: 2023-07-22 13:33:05
tags:
categories:
  - 學習
---

最近把自己原本的靜態履歷網頁用 hexo 改成了部落格，筆記幾點 hexo + Github page 的操作過程，最後補一點套用 NexT 樣式的筆記。

<!-- more -->

# 快速帶過安裝
跟著官方文件走 

- 安裝 Git
- 安裝 Node.js
- 安裝 Hexo

```bash
$ npm install -g hexo-cli
```
到這邊，已經可以使用 `npx hexo <command>` 的指令了
如果想要更縮短指令，則可以在 `~/.zprofile` 中設定 `node_modules/` 資料夾的相對路徑

```bash
$ echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.zprofile
```
這樣就可以使用`hexo <command>`的指令來操作。

# 設定
再來先用指令建出網誌的資料夾，資料夾名稱`<folder>`可以換成任何想要的名字。
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
建立出來的網誌資料夾的結構如下

```
.
├── _config.yml: 設定檔
├── package.json:安裝的套件
├── scaffolds:這個資料夾裡會放一些模板，預設有 draft, page, post 三種
├── source
|   ├── _drafts:我其實沒有這個資料夾
|   └── _posts:文章存放的地方
└── themes:如果從 git clone 樣式下來的話，可以放在這個資料夾
```

這時跑指令
```
$ hexo server
```
就可以開啟瀏覽器到 `http://localhost:4000/` 看目前網誌生成的樣子了。

# 建立頁面

頁面建立的模式預設有三種，就是scaffolds底下看到的三種，姑且稱作草稿(Draft)模式，頁面(Page)模式跟文章(Post)模式，不管哪一種都是用這個語法建立頁面

```
$ hexo new [layout] <title>
```
而這三種模式到底差在哪？以下是我個人的用法

1. 文章模式
```
hexo new post my-note
```
這應該會是之後最常用的，就是按照日期產生文章，當下玩指令hexo就會在`source/_posts`資料夾下建立出`my-note.md`的檔案，當把文章寫完之後在跑

```
$ hexo generate
```
第一次跑完之後會看到網誌的資料夾下多了一個public資料夾，剛才產生的文章就會在Public資料夾中日期的資料夾底下，產生出一篇 html 檔案，而這篇文章的路徑長得會像這樣 `localhost:4000/2023/07/23/my-note/`。

2. 頁面模式
如果我今天想要產生一個普通的頁面，跟照日期的網誌不一樣，不想要產生在 _posts 資料夾底下，就可以用頁面模式。
舉個常見的例子，我想要建立一個關於我的頁面，而我希望他的路徑是 `localhost:4000/about/`

這時就可以下
```
hexo new page --path about/index "About me"
```
就會在`source/about/index.md`的檔案。
記得這邊標題是必填的，如果沒有填寫的話，hexo就會在`source/_posts`資料夾下建立出`source/_posts/about/index.md`的文章。

同樣在編輯完後跑指令`hexo generate`(或縮寫`hexo g`)，就會產生出對應的 html 檔案。

3. 草稿模式
草稿模式建立的語法跟前面很類似，只是 layout 換成了 draft
```
hexo new draft say-hi
```
Markdown檔案會建立在 _drafts 這個資料夾中，當跑指令`hexo g`的時候，可以發現在Public字料夾中不會特別產生 say-hi 的文章或頁面，這就是草稿模式。

如果今天編輯完這個草稿，並且決定他是一篇文章或是頁面以後，需要用`publish`的指令來讓這篇草稿移動到在source資料夾下他該在的位置

```
$ hexo publish [layout] <filename>
```
移動之後執行`hexo g`就會在`Publice`資料夾產生對應的htm檔案。

# 總結
本來想要一口氣寫到部署的，但我光這樣就寫了三天，還是先下個斷點好了。
幾個常用的指令總結一下

1. `hexo server` 是開啟 server
2. `hexo new [layout] <title> ` 是根據模式建立 Markdown 檔案
3. `hexo generate` 或 `hexo g` 在 public 資料夾下建立對應的 html 檔案，也是我們真正可以看到的網頁

這邊剛好都是部署到GitHub page前在本地端會有的操作，所以這篇姑且就叫它本地篇吧。

部署的連結，之後補上。