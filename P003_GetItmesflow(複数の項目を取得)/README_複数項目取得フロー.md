
# Power Automate サンプルフロー：SharePointリストの複数項目取得（完全ガイド）

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
- フローZIP：[GitHubリンク](https://github.com/isamu7pad-alt/powerautomate-flセス**  
   → https://make.powerautomate.com

2. **「ソリューション」または「マイフロー」から「インポート」を選択**

3. **ZIPファイルをアップロード**  
   → ダウンロードしたZIPを選択

4. **接続情報を設定**  
   - SharePoint接続を選択または新規作成
   - 必要に応じて認証情報を入力

5. **保存して完了**  
   → インポート後、フローが「マイフロー」に表示されます

---

## 🛠 一から作成する場合（完全手順）
1. **新しいフローを作成**  
   → 「クラウドフロー」→「インスタントクラウドフロー」→「手動トリガー」

2. **SharePointアクションを追加**  
   → 「複数の項目の取得（Get items）」を選択  
   - サイトアドレス：対象のSharePointサイト  
   - リスト名：対象のリスト名

3. **Composeアクションを追加**  
   → 式に以下を入力：
   ```plaintext
   outputs('複数の項目の取得')?['body/value']


   さらに詳しい解説はこちら
👉 Power AutomateでSharePointリストを取得する完全ガイド（ブログ）

https://www.automate136.com/sharepoint-json/
