---
title: icarusのテーマでHexoを作るとcategoriesとかが404になった件
category:
  - it
tags:
  - Hexo
  - icarus
thumbnail: /img/not_found.thumbnail.jpg
date: 2017-06-10 22:16:32
---

![](/img/not_found.jpg)

Hexoという静的サイトジェネレータがありまして、それをつかって当記事なんかも書いています。

<!-- more -->
<a href="https://px.a8.net/svt/ejp?a8mat=2TKSXI+9ZLU5U+37HI+5ZEMP" target="_blank" rel="nofollow">
<img border="0" width="120" height="60" alt="" src="https://www25.a8.net/svt/bgt?aid=170611830604&wid=001&eno=01&mid=s00000014967001005000&mc=1"></a>
<img border="0" width="1" height="1" src="https://www18.a8.net/0.gif?a8mat=2TKSXI+9ZLU5U+37HI+5ZEMP" alt="">


markdownで書いて、ビルド的なことをすると静的なHTMLに作り替えてくれるやつです。

基本はそれだけのものなんですが、いろいろなテーマをいろいろな人がつくってまして、
それのなかから好きなものを選んで、自分好みのデザインにできるんですね。

で、私が気に入ったやつが
[icarus](https://github.com/ppoffice/hexo-theme-icarus)というテーマです。

このテーマは、

* 記事のサムネイルを指定できる
* サイト内検索ができる
* コメントの受付ができる

というところが特徴といえるでしょうか。
~~(じっくりテーマ選びしてないんでもしかしたら結構他のテーマでもあるかもしれない)~~

や、すごくないですか。
静的なサイトなのにサイト内検索とか、コメント機能とかついちゃっているんですよ。
びっくりですわ。

さっそくテーマの適用をして、github pagesにデプロイして

(´＾ω＾｀)ﾆﾁｬｧ…

ってなってたんですよ。

で、あちこちさわって、検索機能とかもつかって「すげー、ちゃんと動いとるやんけ」と思っていたら

https://***.github.io/categories とかを触ったら
404を返しおった。。。

具体的に言うと

![](/img/not_found_links.png)

こいつら3つが存在しないって怒られた。

マジすか。
このリンクってHexoのテーマであるところの
[icarus](https://github.com/ppoffice/hexo-theme-icarus)さんが自動生成してくれたんだけど、
リンク先存在しないのかよ。。。どうなっとんねん。

ちょっとググったところissuesが立ってて
[`hexo new page categories`してページつくれや](https://github.com/ppoffice/hexo-theme-icarus/issues/236)
みたいなことを言ってた。

ぶっちゃけ「tagsもcategoriesもサイドバーに存在してるんだから別ページとしてわざわざつくらなくてもよくなくなくない？」
と思ったので「それらのページを作る」んじゃなく、「それらへのリンクを消す」ことにした。

どうやら、themes/icarus/_config.yml内の先頭にある「Menus」をみて、リンクを生成しているようだった。
だもんでサクッと削除。

![](/img/delete_menus.png)

これで解決。よしよし。

<a href="https://px.a8.net/svt/ejp?a8mat=2TKSXI+9ZLU5U+37HI+5ZEMP" target="_blank" rel="nofollow">
<img border="0" width="120" height="60" alt="" src="https://www25.a8.net/svt/bgt?aid=170611830604&wid=001&eno=01&mid=s00000014967001005000&mc=1"></a>
<img border="0" width="1" height="1" src="https://www18.a8.net/0.gif?a8mat=2TKSXI+9ZLU5U+37HI+5ZEMP" alt="">