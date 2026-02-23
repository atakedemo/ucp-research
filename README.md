# UCPの調査

## ざっくり進め方

* サンプル実装を動かすための手順を残す
* 気づいたことをメモする

## サンプル実装01 : A2A

* 引用元：[samples/a2a/](https://github.com/Universal-Commerce-Protocol/samples/tree/main/a2a)
* 作業環境:[./sample-a2a/](./sample-a2a/)

### デモ手順

#### 1. AIエージェントバックエンドの立ち上げ

[./sample-a2a/business_agent](./sample-a2a/business_agent)にて実施

**1-1. Python環境を立ち上げる**

```bash
# Pythonのバージョン指定（mac） 
pyenv versions
pyenv local 3.13.3
source ~/.bash_profile

# 2つ目のvenvが仮想環境名
python -m venv venv

#. [仮想環境名]/bin/activate
. venv/bin/activate
```

※終了時

```bash
deactivate
```

**2. ライブラリや環境変数を設定する**

```bash
uv sync
cp env.example .env
```

環境変数には、Gemini実行のためのAPIキーを設定する

```text
GOOGLE_API_KEY=<your gemini api key>
```

**3. サーバーを立ち上げる**

```bash
uv run business_agent
```

<details><summary>サーバー実行時の出力</summary>

```bash
INFO:     Started server process [62192]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://localhost:10999 (Press CTRL+C to quit)
```

</details>

#### 2. サンプルのWebアプリの立ち上げ

