---
title: "Offensive Security Certified Professional (OSCP) 合格体験記"
date: 2021-09-29T09:54:40+09:00
draft: false
categories:
- certification
tags:
- OSCP
---

## 概要

- [Offensive Security Certified Professional (OSCP) ](https://www.offensive-security.com/pwk-oscp/) に合格した
- 合計勉強時間は、4ヶ月ほどでおよそ200時間ちょっと
- 勉強法
  - Lab のMachine を全部解く
  - よく使うけど毎回ググってるようなコマンド系をcheatsheet にまとめる
  - HackTheBox のOSCP-like なマシンを解く/writeup を読んでcheatsheet に加える
  - 他の人の合格体験記などを読む
  - 解けなかったときの振り返り
    - なぜ解けなかったのか、どうすれば解けたのかを考察する
- Lab のレポートは書いていない

## はじめに

今回、Offensive Security Certified Professional (OSCP) というペネトレーションテストの入門資格の試験に合格しました。例のごとく試験内容などは、触れられないため当たり障りの無い感じで、これから受ける人のためになるようなことを書いていきます。  

この手の話は筆者のスペックを語っておいた方が勉強時間や勉強方法などの参考になると思うので少し触れておきます。私自身は、学生の頃(もう4,5年前とか)にCTF でBinary Exploitation やReverse Engineering を専門にやっていました。また、会社入ってからは、インフラエンジニアのような職務内容であるL2/L3設計やネットワーク機器の設定、サーバのメンテナンスなどの運用作業、新規構築プロジェクトなどに携わっていました。また、同時にセキュリティエンジニアのような職務も行っており、主にマルウェア解析を担当しています。そのため、ある程度ペネトレーションテストで問われるようなOffensive Security な知識は持ち合わせていましたが、体系だって勉強したことはありませんでした。特に、Web Security 周りは結構弱いです。また、トレーニング内容や試験内容自体も全部英語なのですが、私自身は英語の読み書きはまぁ普通ぐらいできて、会話も海外旅行程度ならできるといった温度感です。プライベートでは、1歳の子供がいるため、毎日家事育児に追われるお父さんをやっています。以上がざっとした現状のスペックです。

## OSCP とは

この話は、[公式サイト](https://help.offensive-security.com/hc/en-us/articles/360040165632)を見ていただいたほうがわかりやすいと想うので簡単に箇条書きでまとめます。

- Penetration Testing with Kali Linux (PWK) というペネトレーションテストの入門コースに対応した資格試験
  - PWK では、Lab への期限付きアクセス権(私は、90日コースで申し込みました)やPDF/動画教材などが配布されて、基本的に自学自習していくスタイルです
  - 受講者専用のForum などがあり、そこでわからないことは質問したりできますが、直接的な解答はNG とされているため、自力でLab のマシンを解いていく必要があります
- 23時間45分以内に数台のマシンを攻略して、その攻略手順や調査手法などを英語のレポートにまとめて、翌24時間以内に提出します
- マシンを攻略した証であるProof ファイルの提出やそのスクリーンショット、レポートの出来などから総合的に判断されて、ある一定のポイントを超えたら合格となります
- 最初の23時間45分は、カメラで自分自身や操作しているPC の画面を監視されます
  - なお試験用のチャットで連絡することで、自由なタイミングで寝食や休憩などができます

## 勉強方法

### 昨年

実は、もともと昨年OSCP を受験しようと思っていたのですが、いろいろタイミングが悪くなり今回受けた運びになります。そのため、昨年にHack The Box のOSCP-like なマシンを一部解いたりしており、いわゆるマシン攻略がどんな感じなのかといったことはある程度把握していました。

### コース申し込み前1ヶ月(2021年5月)

PWK では、コースの教材のシラバスが公開されているため、事前に目次を読んで自分が知らなそうなことを列挙したり、軽く調べておいたりしました。具体的には、知らないツール名のツールをググって使ってみたり、知らない概念など、忘れかけている知識らへんを復習しました。これをやっておいたおかげで、コースの教材はかなり読みやすかったです。また、同時に試験の公式ルールだったり、試験内容やレポート内容など総合的なこの資格試験に関する情報も収集してまとめていました。他の方の合格体験記や、海外の方の合格体験記など合計10つぐらいは見て内容を抽出したような気がします。

### 1ヶ月目(2021年6月)

まずは、コースの教材として渡されるPDF を2週間で終えることを目標にはじめました。前述したとおり、見るべき箇所など調べておいたので、わかるところはさらさらと斜め読みして、苦手なところや知らないところはしっかり読むということをしました。この間は、特にLab のマシンは実施しませんでした。  
コースの教材を終えたら、その後2週間でLab のマシン攻略に着手しました。もともとHack The Box をやっていたというのもあり、ポートスキャンから初めて、各ポートで動作しているソフトウァやそのバージョンの特定、PoC の検索といった流れは知っていたため、それ通りにやっていきました。最初のうちはなかなか攻略できず、1日1台を目標にしていましたが、できない日も多かったです。家事育児に追われてたというのもあります。また、事前に知っていた、ポートスキャンや各種チェックを行ってくれる[AutoRecon](https://github.com/Tib3rius/AutoRecon) というツールを使うことで寝てる間に検査して朝起きてそれをチェックしながらやっていくというスタイルをとっていました。大体1ヶ月で、33台のマシンを攻略していました。

### 2ヶ月目(2021年7月)

先月に続いてひたすらマシン攻略をやっていました。この頃には、だんだんと慣れてきてサクサク解けるようになってきましたが、Lab のマシンは依存関係があるものが多く、詰まった時はすぐForum を見てヒントを探していました。前述したように直接的な解答はないことが多いので、なんとか推測して読み解いたりしていました。また、この月の中盤には、この当時の全台である75台を攻略しました。その後の半月は、各マシンの復習をしつつcheatsheetを作成することをしていました。また、あえて明言は避けておきますが、慣例的に出るという言われている内容のマシンが存在するため、それに特化した練習をしたりもしていました。そして、残った月でレポート執筆の練習をしていました。

### 3ヶ月目(2021年8月)

私の申し込みタイミング的に、この月の26日でLab へのアクセス権は終了でした。そのため、マシンの復習をしつつレポート執筆の練習を継続していましたが、仕事や家庭が忙しくなり、あまり勉強できていない月でもあります。また、この月には、Udemy で下記の2つのコースを購入して受講したりしました。これらの教材は、前述したAutoRecon の作者によるもので、どちらもOSCP に向けた権限昇格手法について体系的にまとまった教材なためおすすめです。しかしながら、これだけで受からないだろうという感じです。

- [Windows Privilege Escalation for OSCP & Beyond!](https://www.udemy.com/course/windows-privilege-escalation/)
- [Linux Privilege Escalation for OSCP & Beyond!](https://www.udemy.com/course/linux-privilege-escalation/)

この月の下旬には、試験の申し込みをして日時を確定させました。私は、2021年9月26日(日) 8:00 (JST) 開始にしました。この試験時間に関しては、様々な考え方ありますが、私の場合は子供が毎朝5:30に起きるため、昼までどうせゆっくりはできないだろうと思いこの時間帯にしました。結果として頭がよく動く午前中の時間が多かったので良かったと思っています。  
そして、Lab へのアクセス権が終了しました。

### 4ヶ月目(2021年9月)

Lab へのアクセス権がすでに終了しているこの月は、Hack The Box のOSCP-like なマシン攻略に挑戦していました。ググればすぐ出てくるGoogle Spread シートのOSCP より難しいというやつ以外は全部確認しました。また、レポート作成の練習をダラダラと継続していました。後の反省点にも繋がりますが、もっとしっかり気持ち入れてレポート作成練習はやるべきだったなぁと思います。ただ、この月も相変わらずプライベートが忙しく（妻が土日休みではないため、土日基本ワンオペをしているため）後半は、解く時間もないためWriteup だけを読んでcheatsheet にまとめるということをしていました。そうこうしているうちに、試験1週間前になってしまいました。この週では主に以下のことをやりました。

- 試験の注意事項ページや試験時間の監視に関する注意事項ページを読み直す
- 試験中の飲食物の用意
- 当日のイメトレ

## 前日や当日の様子

この商では前日や当日の様子について記載していきたいと思います。

### 試験前日

主に不測の事態が起きたことを考えて下記のようなことを行っていました。
- VM のスナップショット作成と別ラップトップでの展開(試験用マシンが壊れたときのようの対策)
- モバイルルータの充電(自宅のインターネット回線が死んだ時ようの対策)
- 試験フォルダの定期バックアップとGit 管理の自動スクリプトの作成とcron 設定(万が一rm 全消ししたときにすぐに復旧できるようの対策)

### 試験直前

朝は6時ぐらいに起床し、朝ごはんを食べて7時ぐらいには座席についていました。その後、7:45になったら監視ツールの確認などが始まりました。パスポート見せたり部屋の中を徘徊したりしました。予定時刻の8時になったら試験環境へアクセスするためのVPN のコンフィグなどが送られてきたのでつなげたり、試験のインストラクションを読んで各マシンの配点や何をすればいいかなどを確認しました。この**インストラクションかなり重要なのでちゃんと読んだほうがいいです**。ちなみに、VPN の設定をsystemd サービス化して、パスワードファイル作成してそれを読み込むようにしたら、受講者番号やパスワード入力している画面が見れないからダメと言われました。

### 試験中

かなり本質的な部分なのであまりかけることは少ない気がしますが、だいたい3時間ぐらいで初めて1台の攻略に成功しました。その後5時間ぐらい何も解けず、「あ、やべぇ」と焦っていましたが、糸口を見つけた問題を皮切りにして1時間単位ぐらいで解けていき、12時間ほど経過した時点ではすでに合格点数を超える想定の水準まで達していました。残すところ1台のマシンだけだったのですが、どうしてもわからないためある程度のところで見切りをつけて、レポート作成のための証拠保全やスクリーンショットの再確認や、もはやレポートを書き始めることもしていました。もともと4時間ほど睡眠を取る予定でしたが、結局時間が足らず2時間の睡眠で乗り切りました。起きてからもひたすらレポート作成をしたりしていましたが、いかんせん取り忘れたスクショやスクショのときに変なタブ開いてて前後で遷移にずれがあるなどで何回も最初からやり直したりとかしていて無限に時間を溶かしました。論理的な飛躍が生じないように、理屈の通った攻略手順を残せるように冷静になって証拠を保存していくのが良いと思います。結局試験ギリギリまで最後のマシンは何も手がかりがわからずタイムオーバーしました。


### レポート作成/提出

試験が終わって朝ごはんを食べて、すぐ続きを着手していましたが、やはり途中で力尽きて仮眠を入れました。仮眠してスッキリしてから着手したほうが効率が良かったです。結局朝から日付が変わるころまで執筆して、1時間ぐらいかけて提出方法の再確認やファイル名に間違いがないかなどを確認した後に提出しました。朝起きてから見直して提出するか寝る前に提出するか非常に悩んだのですが、もう仮にレポートで落ちても、自分の中ではマシン攻略で合格水準に達していたため、もういいやという気持ちが後押しして寝る前にレポートを提出しました。ちなみに、Lab のレポートは書いていなかったため提出しませんでしたし、何も解けなかった1台のマシンに関してはレポートに記述すらしていませんでした。  
レポート提出の際には、PDFや7zファイル名、容量、解凍したときに余分なファイルや階層が入っていないか、7z に誤ってパスワード付けていないかなど、予め列挙しておいたチェックリストを満たすように検査してから提出しました。

## これから受ける人へ

### レポートの練習をしっかりしてしておこう

少ない時間をうまく有効活用して結構勉強していたつもりなのですが、1つ大きな個人的な反省点を上げるとすれば、レポート作成の練習だったと思います。これが事前にしっかりできており、当日撮るスクリーンショットなども想定しておけば、試験時間やレポート作成事態もここまで大変ではなかったように思います。例えば、一部準備していたものもありますが、主に下記のような点を想定しておくと良いと思います。

- 主語はI なのかWe なのかwe
- 基本的に、現在形で書くのか、過去形で書くのか
- マシンの攻略手順で論理的な飛躍が生じないように、ちゃんと順を追った記録を撮るように練習しておく
- 攻略の手順は、テキストベースで残すのか、スクリーンショットベースで残すのか
- マシン攻略の際に必要となるスクリーンショットの想定
- どのレベルの手順を記載するのか
  - 例) Burp を使ってPOST パラメータを書き換える場合は、Burp の起動やプロジェクトの新規作成のようなところからスクリーンショットを撮るのか否か
  
試験後バイアスな気はしますが、この試験内容が極端に難しすぎるということはないです。ただし、レポートに関しては準備不足だとかなり大変なので、しっかりやることをおすすめします。

### OSCP Exam Guide を頭に叩き込む

[OSCP Exam Guide](https://help.offensive-security.com/hc/en-us/articles/360040165632) と呼ばれる受験やレポート作成/提出の諸注意が記載された本ページは、受験者にとっては必須のページです。認識のズレがないように不安ならば問い合わせて確認したりしてもよいレベルです。私自身何度も読み直しました。

### 試験中はこまめな休憩を取ること

私自身は、予め試験中のスケジュールを立てていました。そのスケジュールでも、こまめな休憩を取るように心がけていました。具体的には1時間に1回5分の休憩ははさみ、昼食や夕食は30分時間を取っていました。なかなか試験中に休憩をするというのが、難しくて試験のことを考えてしまいますが、なるべく頭を空っぽにしてただ休むことに全力を注ぎました。

## おわりに

OSCP は今まで自分が受けてきた資格試験の中で、最も準備が大変な資格試験でした。特に、小さい子供がいる我が家では勉強時間の確保や当日の試験場所の整備は大変でした。勉強を始めた5月末から合格通知が出るまでの間、かなり妻には協力していただきました。特に試験の日は、集中できるようにと娘と二人で昼過ぎぐらいまでおでかけしてくれたり、お風呂やご飯なども全部一人でやっていただきました。改めて、妻に、そしていい子にしててくれた娘に感謝したいと思います。  
本記事が、これからOSCP を受けようと思っている方の参考になれば幸いです。ぜひ、がんばってください。