　この章では、まずDiscordというサービスについて簡単に説明します。次に、本書でBotを作る際に使用するPythonと、PythonでDiscord Botを作る際にもっともよく利用されているライブラリ「discord.py」について紹介します。

## ボイスチャットサービスDiscord

### Discordはゲーマーに大人気
　Discord（ディスコード、https://discordapp.com/）は、2015年に開始したゲーマー向けのボイスチャットサービスです。2019年5月の公式発表によると、ユーザー数は全世界で2.5億人。基本的な機能はすべて無料で利用できます。ゲーマーの間では、オンラインプレイでボイスチャットをするときには、まず選択肢としてあがるサービスです。ボイスチャットがメインのサービスではありますが、テキストチャットも利用できます。代替ツールとしては、Skype、LINEなどが挙げられます。本書のチュートリアルを実践するには、Discordアカウントが必要です。もしDiscordアカウントをお持ちでない場合、まずはアカウント作成を行ってから先に進んでください。

### Discordの特徴を紹介
　Discordでは多彩なコミュニティを作ることが可能です。任意のメンバーを集めたクローズドなコミュニティから、コミュニティに参加するための招待用URLを公開しているオープンなコミュニティまで、Discordにはさまざまなコミュニティがあります。Discordでは、このコミュニティを指して「サーバー」と呼びます。ユーザーが「サーバー」を作成し、そこに他のユーザーを招待します。
　Discordのコミュニティである「サーバー」という名前を本書で使うと、一般名詞の「サーバー」と混同してしまいます。そのため、本書では、Discordの開発者用公式ドキュメントに倣い、このコミュニティのことを以後「**Guild**」と呼ぶことにします。Discordユーザーは、100個までのGuildに参加できます。それぞれのGuildにはいくつかの「チャンネル」があります。テキストチャットは「テキストチャンネル」、ボイスチャットは「ボイスチャンネル」で行います。

## プログラミング言語Python

### Pythonの歴史と特徴
　Pythonは1991年、グイド・ヴァンロッサムによって開発されたプログラミング言語です。オブジェクト指向の言語仕様を持ち、スクリプト言語のためコンパイルが不要で気軽に実行できます。特筆すべき点として、シンプルで覚えやすく、読みやすく書きやすい文法があげられます。インデントによってコードブロックの範囲を示す構文のため、コードの可読性が担保されやすいのです。ブラケット（`{}`）を使ってコードブロックを表現する言語（C++など）ではインデントが文法上の意味を持たないため、インデントはIDEの機能やコーディング者の美意識に委ねられていますが、Pythonでは構造のとおりにインデントを入れないと正しく動かないためバグを排除しやすくなっています。また、できあがったコードは構造とインデントが一致し、美しく読みやすいものになります。

### 強みは豊富なライブラリ
　Python言語のみで実現されている機能は多くありません。ですが、それはシンプルさを保つためにあえてそうしてあり、各種機能は標準ライブラリとして用意されています。必要に応じて標準ライブラリを選択し追加することで多様な機能を使うことができます。Pythonの機能拡張は標準ライブラリだけにとどまりません。強力な数値計算を効率的に行えるNumPyや、データ解析を支援するpandasといった外部ライブラリが充実していることも特徴のひとつです。この本で利用するdiscord.pyも外部ライブラリのひとつです。

### いろんな用途で人気のPython
　2020年現在需要が高まり続けている機械学習に使われる開発言語として、Pythonはファーストチョイスの言語となっています。また、Pythonはその文法的な特徴により初心者にも直感的にわかりやすいため、プログラミング初学者への教育用言語として人気です。外部ライブラリが豊富で、数値計算、画像処理、ウェブアプリケーションのフレームワーク、自然言語処理など、広範囲の開発分野をカバーしています。

## Bot開発フレームワークdiscord.py

### Pythonで一番人気の多機能APIラッパー
　discord.pyは、PythonでDiscord Botを作る際にもっともよく使われているAPIラッパーです。特徴として、モダンなPythonインターフェイス、レートリミット制御、Discord API完全準拠、速度とメモリ効率の両立が挙げられます。GitHubでソースコードが公開されています。

### 強力な拡張フレームワーク
　discord.pyには、基本機能に加えていくつかの拡張フレームワークがあります。拡張フレームワークを使うと、基本機能だけで実装するには手がかかるBotを簡単に実装できます。

#### discord.ext.commands
　`discord.ext.commands`は、コマンドで制御するBotを実装するのに大変役立つフレームワークです。筆者が開発しているshovelも、このフレームワークに沿って設計されています。

#### discord.ext.task
　`discord.ext.task`は、v1.1.0で追加された新しいフレームワークです。1時間ごとに時報を出すなど、定期的な処理をするBotが簡単に実装できます。著者のBot「shovel」でもこのフレームワークを利用し、ログのダンプ処理やBotの稼働状態をDBに出力する処理を実装しています。
