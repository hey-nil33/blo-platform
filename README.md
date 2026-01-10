# blo-platform

**blo-framework / BLO 通信フレームワーク** の親 POM プロジェクトです。  
`blo-comm-core` / `blo-comm-server` / `blo-comm-client` の共通設定とバージョンを一元管理します。

---

## モジュール構成

- `blo-comm-core`  
  共通モデル・アノテーション・署名ユーティリティ・暗号ユーティリティ などのコア層。
- `blo-comm-server`  
  サーバ側の Spring Boot AutoConfiguration・署名検証フィルタ・API ディスパッチャ等。
- `blo-comm-client`  
  クライアント側の HTTP クライアント・設定プロパティ・API 呼び出しラッパ等。

---

## ビルド方法

ルート（このディレクトリ）で以下を実行します。

```bash
mvn clean install
```

これにより：

- `blo-comm-core`
- `blo-comm-server`
- `blo-comm-client`

の 3 つのライブラリがローカル Maven リポジトリにインストールされ、
業務システム（arcx 等）から依存ライブラリとして利用できます。

---

## 業務システムからの利用例

### サーバ側（Spring Boot アプリケーション）

```xml
<dependency>
    <groupId>com.blo</groupId>
    <artifactId>blo-comm-server</artifactId>
    <version>1.0.0-SNAPSHOT</version>
</dependency>
```

### クライアント側（別 Spring Boot サービスなど）

```xml
<dependency>
    <groupId>com.blo</groupId>
    <artifactId>blo-comm-client</artifactId>
    <version>1.0.0-SNAPSHOT</version>
</dependency>
```

---

## 注意事項

- Java 17 以上を想定しています。
- 各モジュールの詳細な使い方は、それぞれの `README.md` を参照してください。
