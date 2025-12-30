
# Power Automate サンプルフロー：SharePointリストの複数項目取得

📌 **このリポジトリについて**  
このリポジトリでは、Power Automateを使って **SharePointリストから複数の項目を取得するフロー** を公開しています。  
初心者でも簡単に試せるよう、フローのZIPファイルとサンプルデータをセットで提供します。  
業務改善やDX推進の第一歩としてぜひ活用してください。

---

## ✅ 特徴
- Microsoft Power Automateを使用
- SharePointリストから複数項目を取得（Get items）
- JSON構造の確認ポイントを解説
- ノーコードで業務効率化を実現

---

## 🚀 フロー概要
- **トリガー**：手動トリガー
- **アクション**：
  1. SharePoint「複数の項目の取得（Get items）」
  2. 作成（Compose）でJSON出力確認
- **目的**：SharePointリストのデータをJSON形式で取得し、後続処理に活用する基礎を学ぶ

---

## 📦 ダウンロード
- フローZIP：`/flows/P002_GetItemsSample.zip`
- サンプルExcel：`/samples/sample_contract.xlsx`

---

## 🔧 インポート手順
1. Power Automateポータルにアクセス
2. 「ソリューション」または「マイフロー」から **インポート** を選択
3. ZIPファイルをアップロード
4. 接続情報（SharePoint）を設定
5. 保存して完了！

---

## 🛠 一から作成する場合
- 手動トリガーを追加
- SharePoint「複数の項目の取得」アクションを設定
- Composeに以下の式を設定：
```plaintext
outputs('複数の項目の取得')?['body/value']
