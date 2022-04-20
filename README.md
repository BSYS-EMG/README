# BSYS GitHub
作成中<br>

## GitHubとは？
超ざっくり説明すると**ソースコード**をオンラインで管理する手段．<br>
ソースコードの管理が前提なので実験データ（画像やcsvファイル）やキャッシュ，外部ライブラリなど容量の大きいファイルは上げない．<br>

## Gitでの管理方法（基礎の基礎）
ここではとりあえずGitにソースコードを保存するためだけの操作を紹介する．<br>
保存先のbrunchを変更や特定のファイルのみの更新はとりあえず考えない．<br>

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

### Step2：アップロードしないファイルを選択
最初に述べたように実験データなどは上げない．<br>
毎回ファイル名を指定して保存するのはめんどくさいので.gitignoreというファイルを作成して保存しないフォルダやファイルを箇条書きしておく．<br>
例えばこんな感じ．書き方はググれば出てくるので細かい指定方法とかは省略
```gitignore
venv/
__pycache__/
*.pth
.ipynb_checkpoints/
```

### Step2：コードをアップロードする
以下のコマンドを作業ディレクトリのterminal/cmdで実行する<br>
branchがmasterじゃなくてmainなのはgithubの意向らしい．2020年にmasterはセンシティブや！ってなって変更されたとか．<br>
mainでもmasterどっちでも問題はない.
Gitで管理してたローカルのファイル上げるときとかはmasterのままでよい．

```terminal
git init
git add -A
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/BSYS-EMG/xx-name-title.git
git push -u origin main
```

### Step3: 変更点をアップロードする（差分を保存する）
2回目からはコマンド3つだけでOK!<br>
```terminal
git add -A
git commit -m "hogehoge"
git push 
```

## 新規ブランチの作成
使用するパッケージを変更するとかアルゴリズムを変更するとかプロジェクトを大きく変更しなければいけない場合はbranchを分けた方が良い．<br>
自分がどこを変更したかわかるように先輩のプログラムやgit cloneしたプログラムから派生させる場合もbranchを分けておくとよい．<br>
branchを分ければバグが起きても本筋のプログラムに影響が起きない．<br>

### Step1：新規branchを作成する
今までは全部`main`ブランチで管理していたので新規ブランチを作成する．<br>
```terminal
git branch branch1
```

## Step2：branchを移動して保存する
Step1ではbranchを作成しただけで作業branchは`main`のままなので移動する必要がある．
```
git checkout branch1
```

### Step3：アップロードする
アップロードの手順はmainの時と同じ
```terminal
git add -A
git commit -m "hogehoge"
git push -u origin branch1
```
