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

> `blo-comm-*` を ArcX 側（`arcx-service` / `arcx-batch`）から参照するため、**先に install しておく**のが安全です。

```bash
cd blo-platform
mvn -U clean install
```

これにより：

- `blo-comm-core`
- `blo-comm-server`
- `blo-comm-client`

の 3 つのライブラリがローカル Maven リポジトリにインストールされ、
業務システム（arcx 等）から依存ライブラリとして利用できます。

---
