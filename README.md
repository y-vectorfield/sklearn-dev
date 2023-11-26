# sklearn-dev
scikit-learnへのContributionを実施する時に利用する資材

## Usage

1. このリポジトリを適当な場所にクローン

```bash
git clone https://github.com/y-vectorfield/sklearn-dev.git
```

2. クローン完了後、`sklearn-dev`ディレクトリ配下に移動

```bash
cd sklearn-dev
```

3. `dev`ディレクトリを作成し、配下にscikit-learnのリポジトリ(公式のfork)をクローン

```bash
mkdir dev
```

4. コンテナイメージをビルド

```bash
docker image build -t sklearn-dev:v23.11 docker/
```

5. ビルドしたイメージからコンテナを起動

```bash
docker container run -it -d -v $PWD/dev:/home/skuser/dev --name sklearn-dev sklearn-dev:v23.11 
```

6. コンテナにログインする時は`skuser`を指定してログイン

```bash
docker container exec -it -u skuser sklearn-dev /bin/bash
```

7. `dev/scikit-learn`配下に移動

```bash
cd dev/scikit-learn/
```

8. Editable modeでscikit-learnをインストール

```bash
pip install -v --no-use-pep517 --no-build-isolation -e .
```
