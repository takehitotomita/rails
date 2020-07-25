# 5章【投稿機能を作ろう】

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
   1. `continuous_exercise_05`というBranchを作成して移動して下さい。
      1. `git checkout -b continuous_exercise_05`
   1. Branchの現在地を確認して下さい。
      1. `git branch` ※`continuous_exercise_05`Branchであれば良い。

**ここまで行ったら教科書に戻り**、読み進みながら、適宜指示のある箇所に関しては、ファイルを編集していきましょう。

教科書を読み終えたら、以下を行ないましょう。
1. ご自身のPC内のローカルリポジトリでの作業
   1. 以下のコマンドを実行し、リモートリポジトリに反映します。
      1. `git add .`
      1. `git commit -m "何かしらのメッセージ"`
         1. 適切なコミットメッセージは学習済みであると思うので、お忘れの方はそちらを復習してみて下さい。
      1. `git push origin continuous_exercise_05`
1. リモートリポジトリ(GitHub)での作業
   1. `continuous_exercise_05`Branchに切り替える。
   1. `master`に向けてPull Requestを作成して下さい。

以上で、継続課題の提出は完了です。

---
## 確認問題
※「解答/解説」を見る前に、1度考えて解答した後、ご自身で解答を確認しながら学んで下さい。
### 問1
ストロングパラメータの正しい書き方はどれですか。

```
a. 
def list_params
　params.require(:テーブル名).permit(:カラム名１, :カラム名２...)
end

b.
def list_params
　params.require(:モデル名).permit(:カラム名１, :カラム名２...)
end

c.
def list_params
　params.permit(:カラム名１, :カラム名２...).require(:モデル名)
end

d.
def list_params
　params.permit(:カラム名１, :カラム名２...).require(:テーブル名)
end
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
b.
def list_params
　params.require(:モデル名).permit(:カラム名１, :カラム名２...)
end

【解説】
ストロングパラメーターはこの形を覚えてしまうのがここに関してはお勧めします。 
```
</details>

### 問2
「新規投稿用のフォームを作成するときに使う機能」について、正しいものはどれですか。
```
a.  「form_for」である。
b.  「createアクション」である。
c.  「getメソッド」である。
d.  「listメソッド」である。
```

<details>
<summary>解答/解説</summary>
 
```
【解答】
a.  「form_for」である。

【解説】
新規投稿用のフォームを作成するときに使う機能はform_forです。 　b.はコントローラー内のアクションの一つです。 　c.d.はルートのHTTPメソッドです。忘れている場合はルートの設定の仕方をもう一度復習してみてください。 

```
</details>
