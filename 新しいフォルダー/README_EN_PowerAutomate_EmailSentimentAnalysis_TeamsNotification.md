
# ✅ Power Automate Flow: Analyze Email Sentiment and Notify Teams if Negative

---

## 📌 About This Repository
This repository provides a **Power Automate** flow that uses **AI Builder** to analyze the sentiment of incoming Outlook emails.  
If the email is classified as **negative**, the flow automatically sends a notification to **Microsoft Teams**.

This solution helps address common challenges such as:
- Delayed response to complaint emails
- Important messages buried in a crowded inbox
- Reduced customer satisfaction due to slow initial action

You can **import the ready-made ZIP file** or build the flow from scratch using the steps provided.

---

## 🚀 Features
- Built with **Microsoft 365 + Power Automate + AI Builder**
- Sentiment analysis supports **positive, neutral, and negative**
- Negative score is quantified (0–1) for better decision-making
- **Low-Code / No-Code** approach for easy implementation

---

## 📂 Folder Structure
```
/flows
  └ P001_SentimentAnalysisFlow.zip   # Completed flow
/samples
  └ sample_negative_email.txt        # Test email content
PowerAutomate_EmailSentimentAnalysis_TeamsNotification_README_EN.md
```

---

## ✅ Flow Overview and Purpose
The flow consists of the following actions:

---

### 1. **When a new email arrives (V3)**  
- **Category**: Office 365 Outlook  
- **Purpose**: Trigger the flow when a new email is received  
- **Note**: You can add filters for subject or sender if needed.

---

### 2. **Analyze sentiment (AI Builder)**  
- **Purpose**: Classify email text as positive, neutral, or negative  
- **Note**: Also provides sentiment scores (0–1) for each category  
- **Expression for Text Field**:  
```plaintext
@triggerOutputs()?['body/body']
```

---

### 3. **Condition (If)**  
- **Purpose**: Check if sentiment equals "negative"  
- **Expression**:  
```plaintext
@equals(outputs('Analyze sentiment')?['body/responsev2/predictionOutput/result/sentiment'],'negative')
```

---

### 4. **Post message in Teams**  
- **Purpose**: Notify the responsible team immediately  
- **Message Body (HTML)**:  
```html
<p>⚠️ Negative email detected<br>
From: @{triggerOutputs()?['body/from']}<br>
Subject: @{triggerOutputs()?['body/subject']}<br>
Sentiment: @{outputs('Analyze sentiment')?['body/responsev2/predictionOutput/result/sentiment']}<br>
Negative Score: @{outputs('Analyze sentiment')?['body/responsev2/predictionOutput/result/documentScores/negative']}</p>
```

---

## ✅ Import Steps
1. Go to **Power Automate portal** → https://flow.microsoft.com  
2. Navigate to **Solutions → Import**  
3. Select the ZIP file (`P001_SentimentAnalysisFlow.zip`)  
4. Configure connections:
   - Outlook: Your Microsoft 365 account
   - Teams: Select the team/channel for notifications
   - AI Builder: Requires a premium license
5. Save and turn on the flow

---

## 🛠 Build from Scratch
- Outlook trigger → AI Builder Sentiment Analysis → Condition → Teams notification

---

## 🔍 Test Method
- Send the sample email (`sample_negative_email.txt`) to your Outlook account  
- If Teams receives the notification, the flow works successfully

---

## 🔗 Related Links
- Blog article: [Step-by-step guide](https://your-blog-url)
- YouTube video: [Watch the tutorial](https://your-youtube-url)

---

## 📜 License
MIT License

⭐ If you find this useful, please give it a Star!
