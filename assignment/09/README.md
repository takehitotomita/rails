# 9章【削除機能を作ろう】

## 課題概要
 - 継続課題 : 1問
 - 確認問題 : 2問

---
## 継続課題
教科書を読み進める前に、以下の準備を行ないましょう。

1. ご自身のPC内のローカルリポジトリでの作業
   1. まず、ターミナル（WindowsはGit Bash)上でご自身のPC内のローカルリポジトリに移動して下さい。
   1. `git pull`をして下さい。
   1. `master`Branchに移動して下さい。
      1. `git checkout master`
   1. Branchの現在地を確認して下さい。
      1. `git branch` ※`master`Branchであれば良い。
   1. `continuous_exercise_09`というBranchを作成して移動して下さい。
      1. `git checkout -b continuous_exercise_09`
   1. Branchの現在地を確認して下さい。
      1. `git branch` ※`continuous_exercise_09`Branchであれば良い。

**ここまで行ったら教科書に戻り**、読み進みながら、適宜指示のある箇所に関しては、ファイルを編集していきましょう。

教科書を読み終えたら、以下を行ないましょう。
1. ご自身のPC内のローカルリポジトリでの作業
   1. 以下のコマンドを実行し、リモートリポジトリに反映します。
      1. `git add .`
      1. `git commit -m "何かしらのメッセージ"`
         1. 適切なコミットメッセージは学習済みであると思うので、お忘れの方はそちらを復習してみて下さい。
      1. `git push origin continuous_exercise_09`
1. リモートリポジトリ(GitHub)での作業
   1. `continuous_exercise_09`Branchに切り替える。
   1. `master`に向けてPull Requestを作成して下さい。

以上で、継続課題の提出は完了です。

---
## 確認問題
※「解答/解説」を見る前に、1度考えて解答した後、ご自身で解答を確認しながら学んで下さい。
### 問1
ルーティングに関して、間違っているものはどれでしょうか。

```
a. パス名は、as:以下で作成できる。
b. パスを全て同じ名前にすることができる。
c. destroyアクションでは、ルーティングでdeleteを使用する。
d. ルートを作成するとき、コントローラーにdestroyアクションを定義しておく必要がある。
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
b. パスを全て同じ名前にすることができる。

【解説】
名前付きパスを同じ名前にすることはできません。
```
</details>

### 問2
link_toの変更について、間違っているものはどれでしょうか。
```
a. link_toの中で、HTTPメソッドを指定できない。
b. link_toは、HTTPメソッドを指定しない場合は自動的にGETになる。
c. form_forは、POSTメソッドが初期設定になる。
d. link_toの引数は、{ method: :delete }とハッシュで指定する。{ }は省略もできる。
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
a. link_toの中で、HTTPメソッドを指定できない。

【解説】
link_toの中でHTTPメソッドを指定することができます。 　例えば 　<%= link_to "表示するテキスト", URL, method: :delete %>
```
</details>
