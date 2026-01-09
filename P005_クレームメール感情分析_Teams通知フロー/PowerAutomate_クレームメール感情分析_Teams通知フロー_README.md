
# ✅ Power AutomateでクレームメールをAI感情分析し、ネガティブならTeams通知するフロー

---

## 📌 このリポジトリについて
このリポジトリでは、**Power Automate**と**AI Builder**を使って、Outlookで受信したメール本文を感情分析し、ネガティブな内容を検知した場合に**Microsoft Teams**へ自動通知するフローを公開しています。

「クレームメールに気づくのが遅れる」「重要なメールが埋もれる」といった課題を解決するための仕組みです。  
ZIPファイルをインポートするだけで簡単に利用できますし、一から自分で作成することも可能です。

---

## 🚀 特徴
- **Microsoft 365 + Power Automate + AI Builder**で構築
- センチメント分析（ポジティブ・ネガティブ・中立）に対応
- ネガティブ度をスコア化し、Teams通知で即対応可能
- **Low-Code / ノーコード**で簡単に業務改善

---

## 📂 フォルダ構成
```
/flows
  └ P001_SentimentAnalysisFlow.zip   # 完成済みフロー
/samples
  └ sample_negative_email.txt        # テスト用メール本文
README.md
```

---

## ✅ フロー概要とアクションの目的
このフローは以下のアクションで構成されています。  
**なぜこのアクションが必要なのか**もあわせて説明します。

---

### 1. **新しいメールが届いたとき (V3)**  
- **カテゴリ**：Office 365 Outlook  
- **目的**：メール受信をトリガーにする  
- **メモ**：クレームメールを検知するための起点です。今回は全メールを対象にしていますが、必要に応じて件名や差出人でフィルタを追加できます。

---

### 2. **センチメントを分析する（AI Builder）**  
- **目的**：メール本文を感情分析し、ポジティブ・ネガティブ・中立に分類  
- **メモ**：ネガティブ度を数値化（0〜1）。日本語対応済みです。  
- **設定する式**（テキスト欄）：  
```plaintext
@triggerOutputs()?['body/body']
```

---

### 3. **条件分岐 (If)**  
- **目的**：ネガティブ判定ならTeams通知へ進む  
- **設定する式**：  
```plaintext
@equals(outputs('センチメントを分析する')?['body/responsev2/predictionOutput/result/sentiment'],'negative')
```

---

### 4. **Teamsにメッセージ投稿**  
- **目的**：対応担当者に即通知  
- **メモ**：差出人・件名・ネガティブスコアを表示して、対応をスピードアップします。  
- **メッセージ本文（HTML形式）**：  
```html
<p>⚠️ ネガティブメールを検知しました<br>
差出人: @{triggerOutputs()?['body/from']}<br>
件名: @{triggerOutputs()?['body/subject']}<br>
判定: @{outputs('センチメントを分析する')?['body/responsev2/predictionOutput/result/sentiment']}<br>
ネガティブスコア: @{outputs('センチメントを分析する')?['body/responsev2/predictionOutput/result/documentScores/negative']}</p>
```

---

## ✅ インポート手順（超丁寧）
1. **Power Automateポータルにアクセス**  
   → https://flow.microsoft.com

2. **「ソリューション」→「インポート」**をクリック  
   → ZIPファイル（`P001_SentimentAnalysisFlow.zip`）を選択

3. **接続設定を確認**  
   - Outlook接続：自分のMicrosoft 365アカウントを選択  
   - Teams接続：通知を送るチームを選択  
   - AI Builder接続：プレミアムライセンスが必要です

4. **保存して有効化**  
   → フローをオンにする

---

## 🛠 一から作成する場合の手順
- Outlookトリガー → AI Builder「センチメント分析」 → 条件分岐 → Teams通知  
※詳細手順はブログ記事で解説しています。

---

## 🔍 テスト方法
- サンプルメール（`sample_negative_email.txt`）をOutlookで送信  
- Teamsに通知が届けば成功です

---

## 🔗 関連リンク
- ブログ記事：[詳細手順はこちら](https://your-blog-url)
- YouTube動画：[動画解説はこちら](https://your-youtube-url)

---

## 📜 ライセンス
MIT License

⭐ このリポジトリが役立ったら、ぜひStarをお願いします！
