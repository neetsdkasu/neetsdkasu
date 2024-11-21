### Hi there 👋
はいぜあ  

 - 永遠のワナビー･･･  
 - 永遠の初心者･･･  
 - 成長のための努力しない永遠のノースキル･･･  
 - 永遠に何者にもなれない･･･  
 


-------------------------------
### げーむ

#### mine sweeper
有名なマインスイーパというゲームぽいやつ  
https://neetsdkasu.github.io/game/minesweeper/  


#### sum10 puzzle
和を10にして消していくゲーム  
https://neetsdkasu.github.io/game/sum10/  


-------------------------------
### つーる

#### DQ-Walk Hearts
ドラゴンクエストウォーク（DQウォーク）のこころセットを雑に求めるツール  
※なお、こころのデータはセルフサービス…  
https://neetsdkasu.github.io/misc/dqwalkhearts.html  

デモ版（ダミーのこころのデータが用意されてる）  
https://neetsdkasu.github.io/misc/dqwalkhearts.html?demo=1  


-------------------------------
### その他

 - GitHub https://neetsdkasu.github.io/
 - GitLab https://neetsdkasu.gitlab.io/
 - Bitbucket https://neetsdkasu.bitbucket.io/


-------------------------------
### 個人的なメモ

<details>

###### 明治維新でスーツとかの西洋文化を標準正装とするなら暦も西暦を標準にしろよクソ  

| 和暦           | 西暦                                               |
|:---------------|:---------------------------------------------------|
| 明治元年9月8日 | 1886年10月23日･･･ （暦が揃ってないタイミング…!?） |
| 明治45年       | 1912年7月30日まで？                                |
| 大正元年       | 1912年7月30日から？                                |
| 大正2年        | 1913年                                             |
| 大正14年       | 1925年                                             |
| 大正15年       | 1926年12月25日まで                                 |
| 昭和元年       | 1926年12月26日から                                 |
| 昭和2年        | 1927年                                             |
| 昭和63年       | 1988年                                             |
| 昭和64年       | 1989年1月7日まで                                   |
| 平成元年       | 1989年1月8日から                                   |
| 平成2年        | 1990年                                             |
| 平成30年       | 2018年                                             |
| 平成31年       | 2019年4月30日まで                                  |
| 令和元年       | 2019年5月1日から                                   |
| 令和2年        | 2020年                                             |


###### 細かい学歴記述要求する履歴書クソ文化消えてくれ…専門職での専門課程修了示す以外での学歴欄を法で禁止しろよクソ

| 事柄         | 和暦        | 西暦      |
|:-------------|:------------|:----------|
| 小学校卒業   | 平成8年3月  | 1996年3月 |
| 中学校卒業   | 平成11年3月 | 1999年3月 |
| 高等学校入学 | 平成11年4月 | 1999年4月 |
| 高等学校卒業 | 平成14年3月 | 2002年3月 |
| 大学入学     | 平成15年4月 | 2003年4月 |
| 大学卒業     | 平成20年3月 | 2008年3月 |

テキトーにググると、『一般的には小学校卒業から書きます』『一般的には中学校卒業から書きます』『一般的には高校入学から書きます』、一般？クソ


###### ページの特定テキスト部分にジャンプさせるURL記述？

```
URL末尾に #:~:text=ほげほげ と付ける
例
https://neetsdkasu.github.io/links.html#:~:text=gist

```



###### goフォーマッタをサブディレクトリ（？）のほうまで適用するやり方


```bash
go fmt ./...
```


###### IPアドレスやホスト名を調べるコマンド（？）

```
dig -x IPアドレス
nslookup IPアドレス
whois IPアドレス
whois ホスト名
```


###### ダウンロードしたファイルのSHAのハッシュ確認方法（？）


```
SHA256ならsha256sum
SHA512ならsha512sum

ハッシュとファイル名だけが分かってるとき
echo ハッシュ ファイル名 | sha256sum -c -

ハッシュとファイル名が並ぶファイルがあるとき(例えばchecksum.txtというファイルなら)
sha256sum -c checksum.txt

```


###### ダウンロードしたファイルのGPG（署名？）とかいうやつの検証方法（？）


```
まず署名した人（？）の情報を登録しとく
ファイルで提供されているなら(ファイル名がfoobar-key.gpg.ascii.txtとするなら)
gpg --import foobar-key.gpg.ascii.txt

署名した人（？）の情報がファイルでなくキーサーバー（？）とかいうとこから取得する必要あるなら
gpg --keyserver キーサーバー名 --recv-key 署名の人のID（ハッシュ？）ぽいやつ

検証用のファイル（拡張子がsigとかascとかある？）を使って検証するらしい
（ダウンロードしたファイルがfoobar.txtで検証用ファイルがfoobar.txt.sigで提供されてるとすると）
gpg --verify foobar.txt.sig

```


###### Androidアプリ作る


```
開発に使ってる実機環境
id: Android-15
Platform: Android 4.0.3
API Level: 15

ターゲット一覧を眺める（ここからターゲットを選ぶ、まぁ現在はAndroid-15だが）
android list targets

ターゲットに対する新規プロジェクト
android create project --target <target-id> --name MyFirstApp \
--path <path-to-workspace>/MyFirstApp --activity MainActivity \
--package com.example.myfirstapp

デバッグビルド
ant debug

デバッグビルドのアプリを実機へ新規インストール（ant用ビルドスクリプトに登録されてるコマンドでも出来た木がする、おそらくant debug install 
adb install bin\MyFirstApp-debug.apk

デバッグビルドのアプリを実機へ再インストール（ant用ビルドスクリプトに登録されてるコマンドでも出来た木がする）
adb install -r bin\MyFirstApp-debug.apk

実機からアンインストール（ant用ビルドスクリプトに登録されてるコマンドでも出来た木がする）
adb uninstall com.example.myfirstapp

開発作業をやめるときにバックグラウンドで稼動してる実機と通信するデバッグサーバーを停止（antやadbでコマンド実行すると起動するぽい？）
adb kill-server

android-sdk-windows\tools\ant\build.xml にあるコマンドぽいもの(targetタグの一部)
ant helpを実行でこれらの説明が並ぶぽい

ant clean
ant release
ant test
ant lint
ant debug install
ant release install
ant installd
ant installr
ant uninstall
ant help

細かい設定に困ったらIDPWMemoICSを見る

android create projectしたあとに最初に ant debug で空ビルドしてから ant lint をやっておく(lintはビルド時に生成されるデータがないと動かない)
この際に出るエラーはIDPWMemoICSの設定ファイル等を参考にする
たいていの場合、
AndroidManifest.xmlの
  manifestタグ下に
    <uses-sdk android:minSdkVersion="15" android:targetSdkVersion="15" />
    を書いておく
  applicationタグの属性に
    android:allowBackup="false"
    を追加しとく
local.propaertiesの
　　sdk.dirの値のパスのコロン(:)の文字をエスケープ文字(\)でエスケープする
ant.propertiesに
  java.compilerargs=-Xlint -Xlint:-options
  の行を書き込む
lint.xmlを作成して
  <?xml version="1.0" encoding="UTF-8"?>
　　<lint>
      <issue id="IconMissingDensityFolder" severity="ignore" />
      <issue id="GoogleAppIndexingWarning" severity="ignore" />
      <issue id="OldTargetApi" severity="ignore" />
  </lint>
  を書いておく

USBデバッグは
自分のアプリだけの眺めるなら、Log.d("MyApp", "hoge") とかしてるなら
リアルタイムで眺めるなら
adb logcat ActivityManager:I MyApp:D *:S
直近の情報だけでいいならリダイレクトでlogfile.txtに書き込むなら
adb logcat -d ActivityManager:I MyApp:D AndroidRuntime:E *:S > logfile.txt
とコマンド打てばOK（ :D はデバッグレベルのログ表示、　:S は一切見えなくする ）
*:Sとすることでログに出てくる関心のない他のアプリのログを見えなくできる･･･
ActivityManagerはMyAppの起動とか見る
AndroidRuntimeはMyAppの例外発生で異常終了とか…？

リソースファイル(/res)を弄ったら
ant clean
をしたほうが良さそう
ant cleanしないと反映されてない状況に遭遇したりしたし（ヌルポが出た）

デバッグビルドのapkファイル
グーグルドライブ経由で他のスマホにインストールすることが出来た
スマホ間の通信のテストとか可能ということがわかった

ヘルプ
android --help
adb help
adb logcat --help
ant -help   これはant自身のヘルプ
```

</details>
