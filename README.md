# example_poetry

Pythonのパッケージマネージャ:poetryを検証するためのリポジトリ
スクリプトの登録やライブラリの管理を行うので、npmのイメージ

## poetryのinstall

```bash
pip install poetry
```

## プロジェクトのセットアップ
```
poetry new poetry_venv
```
## 既存のディレクトリに作る場合
設定が多めなので、面倒かも
```
poetry init
```

## ライブラリのinstall
```
poetry add library_name
```
poetry.lockファイルが作成される

whlファイルのinstall 
```
poetry add dist/kenimo_lib-0.1-py3-none-any.whl
```

### ライブラリの削除
```
poetry remove library_name
```

## poetry.lockファイルがある場合の環境構築
```
poetry install
```

## poetryで作成されたvirtual-envを確認する
```
poetry env use python
```


## pythonファイルの実行
```
poetry run python script/hello.py 
```

## スクリプトを実行
pyproject.tomlにスクリプト定義とスクリプトを配置するフォルダを記載する

pyproject.toml
```
[tool.poetry]
packages = [
    { include="scripts" },
]

[tool.poetry.scripts]
hello = "scripts.hello:main"
```

実行
```
poetry run hello
```

## 参考
[Poetryをサクッと使い始めてみる](https://qiita.com/ksato9700/items/b893cf1db83605898d8a)
[python-poetryのinstall方法のドキュメント](https://install.python-poetry.org)
[poetryでパッケージ・仮想環境を管理](https://rinoguchi.net/2020/06/poetry.html)
