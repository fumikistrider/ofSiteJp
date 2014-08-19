# openFrameworks日本語サイトopenFramewroks日本語版サイト[openFrameworks.jp](http://openframeworks.jp/)を生成するコンテントを管理しているリポジトリです。翻訳作業に協力していただける方は、以下のメールアドレスにご連絡ください。* 田所淳 ([tadokoro@gmail.com](tadokoro@gmail.com))## サイトをローカルに構築するためのセットアップ翻訳をお手伝いしていただける方は、まずリポジトリをForkして、ローカルマシンにダウンロードします (参考：[Help.GitHub - Fork A Repo](http://help.github.com/fork-a-repo/))。ローカルのマシンには、Pythonと、lxml、[blogofile](http://blogofile.com/) がインストールされている必要があります。Pythonがインストールされたマシンであれば、以下の手順でインストールできます:	easy_install lxml	easy_install blogofileサイトを生成してローカルマシンで閲覧するには、以下のコマンドを実行します。	blogofile build	blogofile serve## 日本語版のTips日本語版のブログを、blogofileでビルドする際に、下記のようなエラーが出てビルドに失敗することがあります。~~~~$ blogofile buildERROR:blogofile.filter:Cannot load filter: rst_templateTraceback (most recent call last):... 中略 ...raise ValueError, 'unknown locale: %s' % localenameValueError: unknown locale: UTF-8~~~~これは、文字コード（ロケール）の設定に付随する問題のようです。ビルドするシェルのロケール設定を「US.UTF-8」にすることで解決します。例えば、bashで作業している場合はユーザーのホームディレクトリ直下にある .bash_profile ファイルに下記の設定を追加することで、エラーを回避することが可能です。~~~~export LC_ALL=en_US.UTF-8export LANG=en_US.UTF-8~~~~2014年8月現在、下記の構成でビルドできることを確認しています。- Python 2.7.6- Blogofile 0.8b1## Markdown記法についてサイトの文書は、Markdownというwikiに似た書式で記述します。詳細は、[Daringfireball](http://daringfireball.net/projects/markdown/)を参照してください。(参考：[Markdown文法の全訳](http://blog.2310.net/archives/6))コードの断片を挿入する際には、下記のように記述します。	~~~~{.cpp}	for(int i = 0; i < 16; i++) {		ofLog() << i;	}	~~~~画像は通常のMarkdown記法で記述します。	![Image Title](filename.png "alt text")## Markdownのためのテキストエディター別の方法として、bogofilesを使用しないでもローカルでHTMLのレンダリング結果を参照しながら編集できるエディターが使用可能です。* Mac OSX: [Mou](http://mouapp.com/)* Windows: [MarkdownPad](http://www.markdownpad.com/)* Linux: [Writr](http://antrix.net/pages/writr-markdown/), [ReText](http://sourceforge.net/p/retext/home/ReText/), & the [gedit-markdown](http://www.jpfleury.net/en/software/gedit-markdown.php) plugin※このサイトでは、Markdownの文法に機能を追加しています。ですので、エディターではコードハイライトのような特殊機能はエディターでは確認できません。こうした部分はサイトで確認しながら進めてください。