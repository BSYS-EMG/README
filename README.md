# BSYS GitHub
作成中<br>

## 新たに投稿する
### Step1：リポジトリを作る
<img src="img/step1.png"><br>
① 画像にあるように"New repository"を開く<br>
<img src="img/step2.png"><br>
② Ownerを個人から**BSYS-EMG**に変更する．<br>
③ 「卒業年-名前-タイトル」と名前を付ける<br>
④ 研究室内のみでの共有なので**Private**とする<br>
⑤ レポジトリを作成<br>
<img src="img/step3.png">
このような画面が出てきていれば作成完了<br>

### Step2：コードをアップロードする
以下のコマンドを作業ディレクトリのterminal/cmdで実行する<br>
```
git init
git add -A
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/BSYS-EMG/xx-name-title.git
git push -u origin main
```
## よく使うgitコマンド
``` terminal
# 作業ディレクトリにGitを使う宣言をする
git init

# 変更したファイルやディレクトリをステージにあげる
# 特定のファイル／ディレクトリを上げる場合
git add hogehoge.py
# 変更されたファイル／ディレクトリ全てを上げる場合
git add -A
```
