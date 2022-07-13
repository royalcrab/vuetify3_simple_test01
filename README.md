# レポジトリの複製方法

このリポジトリの内容を複製して、新たなリポジトリを作成する方法です。

## 手順

1. github に新しいリポジトリを作成します。

以下では、新しいレポジトリの名前を new_project としたとします。

2. このリポジトリのベアクローンを作成します。

```
$ git clone --bare git@github.com:royalcrab/vue3-vuetify3-template.git
```

3. 新しいリポジトリにミラープッシュします。

```
$ cd vue3-vuetify3-template
$ git push --mirror git@github.com:yourname/new_project.git
```

4. クローンしたローカルリポジトリを削除します。

```
$ cd ..
$ rm -rf vue3-vuetify3-template.git
```

5. あらためて、新しいレポジトリを clone します。

```
$ git clone git@github.com:yourname/new_project.git
$ cd new_project
```

6. 起動テスト

```
$ yarn dev
```

ブラウザで http://localhost:3000 を開いて、ページが表示されたらOKです。