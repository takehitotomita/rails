# 3章【Railsでアプリケーションを開発しよう】

## 課題概要
 - 継続課題 : 1問
 - 確認問題 : 3問

---
## 継続課題
教科書で作成したRailsアプリケーションと全く同じ状態のものを、本リポジトリに用意しております。

今後、本リポジトリのファイルに追加変更していきます。

そのため、**教科書内で作成した`sample_app`は今後使いません。**

今回の継続課題では、本リポジトリをVagrantで動くように設定していきましょう。

以下の手順に従って作業して下さい。
1. vagrantにSSH接続して下さい。
   1. 接続していない場合は`vagrant ssh`というコマンドを入力してEnterキーを押して下さい。
1. `/home/vagrant/work`に移動して下さい。
   1. 移動してない場合は`cd /home/vagrant/work`というコマンドを入力してEnterキーを押して下さい。
1. 本リポジトリを`git clone`して下さい。
   1. `git clone https://github.com/web-camp/03_rails_assignment-sample_app-[ご自身のGitHubアカウントID].git`というコマンドを入力してEnterキーを押して下さい。
      1. [ご自身のGitHubアカウントID]という箇所は適宜、適切なものに変更して下さい。
      1. URLは任意の場所からコピーしてくることをオススメします。
1. `clone`したディレクトリに移動して下さい。
   1. `cd 03_rails_assignment-sample_app-[ご自身のGitHubアカウントID]`というコマンドを入力してEnterキーを押して下さい。
      1. [ご自身のGitHubアカウントID]という箇所は適宜、適切なものに変更して下さい。
      1. ディレクトリ名は`ls -al`で確認する事をオススメします。
1. railsサーバを起動して下さい。
   1. `rails s -b 0.0.0.0`
1. [http://localhost:3000/top](http://localhost:3000/top)にアクセスして、以下のような画面になれば成功です。
<img width="410" alt="スクリーンショット 2020-05-11 8 03 57" src="https://user-images.githubusercontent.com/55776672/81513680-23cf7580-9365-11ea-9581-64d68c8d1b37.png">

---
## 確認問題
※「解答/解説」を見る前に、1度考えて解答した後、ご自身で解答を確認しながら学んで下さい。
### 問1
仮想環境のあるディレクトリまでの移動方法として、正しいものはどれですか。

（現在、デスクトップにいるものとします）

```
a. cd vagrant/work
b. vagrant/work
c. cd work/vagrant
d. work/vagrant
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
c. cd work/vagrant

【解説】
フォルダの中に入るにはcdコマンドを使う必要があります。 さらにworkフォルダの中にあるvagrantフォルダの中に行きたいのでwork,vagrantの順番になっているものが正解となります。 No such file or directoryのようなエラーが出た場合は間違っているディレクトリやファイルにいる可能性が高いです。

```
</details>


### 問2
仮想環境をシャットダウンさせるコマンドはどれですか。

```
a. vagrant up
b. vagrant halt
c. vagrant reload
d. vagrant suspend
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
b. vagrant halt

【解説】
vagrantをシャットダウンするコマンドvagrant haltが正解となります。

```
</details>


### 問3
次のうち、間違っているものはどれですか。

```
a. コントローラを作成するコマンドは、「rails g controller コントローラ名」である。
b. ルーティングの記述方法は、「HTTPメソッド 'URL' => 'アクション#コントローラ名'」である。
c. Railsサーバを起動するコマンドは、「rails s -b 0.0.0.0」である。
d. アプリケーションのひな形を作るコマンドは、「rails new アプリケーション名」である。
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
b. ルーティングの記述方法は、「HTTPメソッド 'URL' => 'アクション#コントローラー名'」である。

【解説】
正確なルートの書き方はコントローラー名#アクションの順番です。アクションがしっかりと定義してないとエラーが出ます。その時はroute errorではなくsyntax errorやno method errorが出ます。

```
</details>
