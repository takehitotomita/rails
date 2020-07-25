# 6章【閲覧機能を作ろう】

## 課題概要
 - 継続課題 : 1問
 - 確認問題 : 4問

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
   1. `continuous_exercise_06`というBranchを作成して移動して下さい。
      1. `git checkout -b continuous_exercise_06`
   1. Branchの現在地を確認して下さい。
      1. `git branch` ※`continuous_exercise_06`Branchであれば良い。

**ここまで行ったら教科書に戻り**、読み進みながら、適宜指示のある箇所に関しては、ファイルを編集していきましょう。

教科書を読み終えたら、以下を行ないましょう。
1. ご自身のPC内のローカルリポジトリでの作業
   1. 以下のコマンドを実行し、リモートリポジトリに反映します。
      1. `git add .`
      1. `git commit -m "何かしらのメッセージ"`
         1. 適切なコミットメッセージは学習済みであると思うので、お忘れの方はそちらを復習してみて下さい。
      1. `git push origin continuous_exercise_06`
1. リモートリポジトリ(GitHub)での作業
   1. `continuous_exercise_06`Branchに切り替える。
   1. `master`に向けてPull Requestを作成して下さい。

以上で、継続課題の提出は完了です。

---
## 確認問題
※「解答/解説」を見る前に、1度考えて解答した後、ご自身で解答を確認しながら学んで下さい。
### 問1
正しいものはどれですか。モデルはListモデルとします。
```
a. すべてのデータを取り出すメソッドは、List.allメソッドである。
b. すべてのデータを取り出すメソッドは、List.findメソッドである。
c. すべてのデータを取り出すメソッドは、List.titleメソッドである。
d. すべてのデータを取り出すメソッドは、List.bodyメソッドである。
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
a. 全てのデータを取り出すメソッドはList.allというメソッドである。

【解説】
allメソッドがモデルから全てのデータを取ってきてくださいという指示です。 findメソッドが一つのレコードを取ってくる指示です。 titleとbodyはコントローラーでこのように使われることはありません。

```
</details>

### 問2
ループ処理の正しい書き方はどれですか。
```rb
a. 
<%= @lists.each do |list| %>
   タイトル
   <%= list.title %>
<% end %>

b.
<%= @lists.each do |lists| %>
   タイトル
   <% list.title %>
<% end %>

c. 
<% @lists.each do |list| %>
   タイトル
   <%= list.title %>
<% end %>

d. 
<% @lists.each do |lists| %>
   タイトル
   <%= list.title %>
<% end %>
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
c. 
<% @lists.each do |list| %>
   タイトル
   <%= list.title %>
<% end %>

【解説】
|ブロック変数|の中身と.titleの前のローカル変数を一致させないと繰り返し処理が行われないので繰り返し処理ができない場合はこの部分をチェックしてみてください。

```
</details>

### 問3
投稿データは、URLの/todolists/:idに含まれるidで判別するようにしました。この「:id」に入っている値をアクション内で取得するには、どれが正しいでしょうか。
```rb
a. 
def show
   @list = List.find.params[:id]
end

b.
def show
   @list = List.find[params[:id]]
end

c.
def show
   @list = List.find[:id]
end

d.
def show
   @list = List.find(params[:id])
end
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
d.
def show
   @list = List.find(params[:id])
end

【解説】
[:id]の状態が正解でfindメソッドの引数にparams[:id]を持ってきているのでd.の形が正解となります。

```
</details>

### 問4
記事一覧ページから詳細ページへのリンクを作成する方法は、どれが正しいでしょうか。
```rb
a. <%=link_to 表示するテキスト, "リンク先URL" %>
b. <%=link_to リンク先URL, "表示するテキスト" %>
c. <%link_to 表示するテキスト, "リンク先URL" %>
d. <%link_to リンク先URL, "表示するテキスト" %>
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
a.<%=link_to 表示させるテキスト, "リンク先のURL" %>

【解説】
<% %>と<%= %>の違いはビュー上に表示するかどうかの違いです。表示する場合は<%= %>を使います、なので今回は <%= %>を使っていてリンク先のURLが後に書いてあるa.が正解になります。

```
</details>
