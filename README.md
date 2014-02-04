# grunt-init-localsite

> localhostでアクセスするサイト用プロジェクトを[grunt-init][]ベースで作成するテンプレートです。
> Create a localsite project with [grunt-init][], including Nodeunit unit tests.

[grunt-init]: http://gruntjs.com/project-scaffolding

## Installation
もしgrunt-initをインストールしていなければ、インストールしてください。

If you haven't already done so, install [grunt-init][].

一度インストールが完了すると、`~/.grunt-init/`ディレクトリにテンプレートを入れておくだけでスケルトンの作成が可能となります。テンプレートの保存は次のgitコマンドでできます。

Once grunt-init is installed, place this template in your `~/.grunt-init/` directory. It's recommended that you use git to clone this template into that directory, as follows:

```
git clone git@github.com:heporap/grunt-init-localsite.git ~/.grunt-init/localsite
```

_(Windowsユーザーは[grunt-initのドキュメント][grunt-init]を読んでください。)_

_(Windows users, see [the documentation][grunt-init] for the correct destination directory path)_

## Usage

開発ディレクトリに空のディレクトリを作成し、その中で次のコマンドを入力してください。

At the command-line, cd into an empty directory, run this command and follow the prompts.

```
grunt-init localsite
```

ファイルの生成が完了すると、`git init`コマンドと、`git remote add repository_name repository_local `コマンドを実行します。

repository_name に"none"を指定するとgit remoteは実行しません。

This will run `git init` and `git remote add repository_name repository_local`. If repository_name was set "none", this will not do "git remote".

_このテンプレートはカレントディレクトリの内容を書き換えます。ディレクトリに何もない事を確認してください。_

_Note that this template will generate files in the current directory, so be sure to change to a new directory first if you don't want to overwrite existing files._

_`grunt-init`コマンドを実行した後に`npm install`を実行し、関連するライブラリをインストールしてください。_

_Run `npm install` after grunt-init to instal relative libraries._

## miscellaneous
構成を変更する場合は、Gruntfile.js、package.jsonを改変してください。

Edit Gruntfile.js, package.json to change the constructions.

## grunt commands

```
#grunt
```

コンパイルを行います。

This will compile the files.

```
#grunt public_html
```

**public_html**ディレクトリの中にあるファイルが公開用ディレクトリにコピーされます。
公開用ディレクトリ内では、destの内容は<script src="dest/プロジェクト名.min.js"></script>で読み込めます。
公開ディレクトリのディレクトリ名は、初期設定時の public_html 設問、ならびにpackage.jsonの " public_html " で指定されたディレクトリです。
デフォルトは Sites です。

This will copy files in **public_html directory** to **public_html setting** in package.json. And **dest** directory will be copied in the public_html setting directory. The default setting of public_html setting is "Sites".

```
#grunt public_build
```

コンパイル後に公開ディレクトリにコピーします。

This will copy files to the Sites directory after compiling.
