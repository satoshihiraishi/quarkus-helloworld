# quarkus-helloworld

このプロジェクトはQuarkusとKotlinを使用して作成されたHello Worldアプリケーションです。

## 開発モードでの実行

以下のコマンドでアプリケーションを開発モードで実行できます。これにより、ライブコーディングが可能になります。

```code
./gradlew quarkusDev
```

## アプリケーションのパッケージ化と実行

アプリケーションは以下のコマンドでパッケージ化できます。

```code
./gradlew build
```

これにより、build/quarkus-app/ディレクトリにquarkus-run.jarファイルが生成されます。このファイルを使用してアプリケーションを実行できます。

```code
java -jar build/quarkus-app/quarkus-run.jar
```

## ネイティブ実行可能ファイルの作成

以下のコマンドでネイティブ実行可能ファイルを作成できます。

```code
java -jar build/quarkus-app/quarkus-run.jar
```

また、GraalVMがインストールされていない場合は、以下のコマンドでコンテナ内でネイティブ実行可能ファイルのビルドを行うことができます。

```code
./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true
```

ネイティブ実行可能ファイルは以下のコマンドで実行できます。

```code
./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true
```

## Dockerでの実行

以下のコマンドでDockerイメージをビルドし、Dockerコンテナとしてアプリケーションを実行できます。

```code
docker build -f src/main/docker/Dockerfile.jvm -t quarkus/quarkus-helloworld-jvm .
docker run -i --rm -p 8080:8080 quarkus/quarkus-helloworld-jvm
```

## テスト

以下のコマンドでテストを実行できます。

```code
./gradlew test
```

以上が、このプロジェクトの基本的な使い方です。詳細な情報は[Quarkusの公式サイト](https://quarkus.io/)をご覧ください。

## 備忘録

```code
quarkus create app quarkus-helloworld --kotlin --gradle

./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true -Dquarkus.native.container-runtime=docker

./gradlew imageBuild

## ローカル
docker run -i --rm -p 8080:8080
```
