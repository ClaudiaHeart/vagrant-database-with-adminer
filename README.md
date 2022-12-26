<!-- omit in toc -->
Vagrant Database With Adminer
==========
[![MIT licensed][shield-license]][mit]

自分用の検証ツールです。  
`vagrant up`コマンド一発で`PostgreSQL`と`MariaDB`と`Adminer`を用意できるようにしたものです。  
全て`docker`で実行しています。  


<!-- omit in toc -->
目次
-----------------
<details>
<summary>show</summary>

- [作業環境](#作業環境)
- [ツールのバージョン](#ツールのバージョン)
- [使い方](#使い方)
  - [実行](#実行)
  - [設定ファイルの変更](#設定ファイルの変更)
  - [データの投入](#データの投入)
- [バージョニング](#バージョニング)
- [ライセンス & 作者](#ライセンス--作者)
</details>


作業環境
------------
- Windows 10 64bit
- VirtualBox 7.0.2
- Vagrant 2.3.4


ツールのバージョン
------------
- ubuntu/focal64 v20220924.0.0
- docker-compose 3.7
- [adminer](https://hub.docker.com/_/adminer) 4.8.1
- [mariadb](https://hub.docker.com/_/mariadb) 10.8.3
- [postgres](https://hub.docker.com/_/postgres) 14.4


使い方
-----
### 実行
```pwsh
vagrant up
```

### 設定ファイルの変更
下記のenvファイルから環境変数を変更できる
- [バージョン等の設定](docker\.env)
- [Adminerの設定](docker\.env.adminer)
- [MariaDBの設定](docker\.env.mariadb)
- [PostgreSQLの設定](docker\.env.postgres)

### データの投入
下記ディレクトリに`sqlファイル`を置いておけば、`docker`実行時に`SQL`が実行される
```
docker\mariadb\sql
docker\postgres\sql
```
ちなみにサンプルのデータを既に配置している。
- [MySQL Sample Databases]
- [PostgreSQL Sample Database]



バージョニング
-----
[SemVer][semver]のガイドラインに則ってバージョン管理しています。  
リリースは以下の形式で行われます。
```
<major>.<minor>.<patch>
```
- 大きな変更や後方互換性のない場合は `<major>` (`<minor>` と `<patch>` もリセット) を上げます。
- 後方互換性があり機能性を追加した場合は `<minor>` (`<patch>` もリセット) を上げます。
- 後方互換性を伴うバグ修正をした場合 `<patch>` を上げます。


ライセンス & 作者
-------
[![MIT licensed][shield-license]](LICENSE)  
Copyright &copy; 2022, ClaudiaHeart



[shield-license]: https://img.shields.io/badge/license-MIT-blue.svg
[mit]: https://licenses.opensource.jp/MIT/MIT.html
[semver]: https://semver.org/lang/ja/
[MySQL Sample Databases]: https://www3.ntu.edu.sg/home/ehchua/programming/sql/SampleDatabases.html
[PostgreSQL Sample Database]: https://www.postgresqltutorial.com/postgresql-getting-started/postgresql-sample-database/