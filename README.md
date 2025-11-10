# n8n Automation Hub — Social, Media & Crypto Toolkit

A curated set of production-ready **n8n** workflows for social media automation, content pipelines, file handling, and crypto/trading notifications.  
Each workflow is saved as an n8n-exportable `.json` file and includes a short description, inputs, outputs, and required credentials.

---

## ▶️ Quick Start

1. **Clone or download** this repo.
2. Open your n8n instance (self-hosted or n8n Cloud).
3. **Import** a workflow:  
   `n8n → Workflows → Import from file → select any .json here`
4. Update any **Credentials / Environment variables** shown in each workflow’s notes.
5. **Activate** the workflow and test.

> Tip: If you want to rename your local files exactly like below, use the included scripts:  
> `rename-n8n.ps1` (Windows PowerShell) or `rename-n8n.sh` (Linux/macOS).

---

## 📦 Included Workflows

| Filename | Description |
|---|---|
| `Reddit-Memes_to_GDrive-Dedupe_Telegram-Alerts.json` | Monitors meme subreddits, downloads images to Google Drive, prevents duplicates, and sends Telegram alerts. |
| `Reddit-Image_to_Facebook-Photo_AutoPoster.json` | Pulls image posts from Reddit and publishes them automatically to a Facebook Page as photo posts. |
| `Terabox-Link_to_Direct-Download_Telegram-Sender.json` | Converts Terabox links to direct-download links and forwards them to a Telegram chat or channel. |
| `AI-Scalping_Signals-Binance_Bybit_to_Telegram.json` | Collects trading signals, checks pairs on Binance/Bybit, and relays formatted alerts to Telegram. |
| `Reddit-Memes_to_GDrive-Dedupe_Telegram-Alerts_v2.json` | Enhanced version of the Reddit→Drive pipeline with improved deduplication and Telegram notifications. |
| `Drive-Folder_to_YouTube_Uploader_AI-Title-Tags.json` | Watches a Google Drive folder; when new videos appear, generates AI titles/descriptions/tags and uploads them to YouTube automatically. |
| `Drive-Video_to_FB-IG-Telegram_Multipost.json` | Takes videos from Drive and cross-posts them to multiple platforms (Facebook, Instagram, Telegram). |
| `Telegram-Shop_Assistant_Image-Analyze_to_Sheets-Match_BN.json` | Telegram-based shop/product assistant: analyzes images, logs results to Google Sheets, and matches products or SKUs (Bangla-friendly). |
| `Telegram-CryptoPair_to_Binance_15m-1h-1d_Analyzer.json` | Accepts a crypto pair via Telegram, fetches Binance data, computes metrics for 15m/1h/1d intervals, and returns formatted analysis. |

---

## 🔧 Requirements

Most workflows require one or more of the following:

### Credentials
- Telegram Bot API Token (via [@BotFather](https://t.me/BotFather))
- Reddit API Client ID and Secret
- Google Drive / Google Sheets (OAuth2 or Service Account)
- Facebook/Instagram (Graph API credentials)
- YouTube Data API
- Binance / Bybit (public endpoints usually fine for market data)

### n8n Nodes
- Core n8n nodes: **HTTP Request**, **IF**, **Switch**, **Set**, **Function/Function Item**
- App-specific nodes: Telegram, Reddit, Google Drive, Sheets, YouTube, Facebook/Meta, Binance, Bybit

### Optional Environment Variables
TELEGRAM_CHAT_ID=
TELEGRAM_CHANNEL=
GDRIVE_FOLDER_ID=
YOUTUBE_CATEGORY_ID=

yaml
Copy code

Each workflow includes inline notes indicating required credentials and variables.  
After importing, open the nodes with credential warnings and connect your accounts.

---

## 🧪 Testing

- Use **Manual Execution** in n8n to step through with sample inputs.  
- For **webhook triggers**, click **Test** to get a temporary endpoint.  
- For **scheduled jobs**, set a short cron interval (e.g., every minute) while testing.

---

## 🚀 Deployment Tips

- Keep imported workflow names consistent with filenames.  
- Store all tokens in **n8n Credentials** or a secrets manager.  
- Add **error handling branches** to send Telegram/Slack logs.  
- Watch for **API rate limits** and include delays or retries.  
- Consider adding a lightweight **Google Sheet or DB log** for summary reports.

---

## 🗂️ Repo Structure

.
├─ README.md
├─ rename-n8n.ps1 # Windows: safe rename script
├─ rename-n8n.sh # Linux/macOS: safe rename script
├─ Reddit-Memes_to_GDrive-Dedupe_Telegram-Alerts.json
├─ Reddit-Image_to_Facebook-Photo_AutoPoster.json
├─ Terabox-Link_to_Direct-Download_Telegram-Sender.json
├─ AI-Scalping_Signals-Binance_Bybit_to_Telegram.json
├─ Reddit-Memes_to_GDrive-Dedupe_Telegram-Alerts_v2.json
├─ Drive-Folder_to_YouTube_Uploader_AI-Title-Tags.json
├─ Drive-Video_to_FB-IG-Telegram_Multipost.json
├─ Telegram-Shop_Assistant_Image-Analyze_to_Sheets-Match_BN.json
└─ Telegram-CryptoPair_to_Binance_15m-1h-1d_Analyzer.json

yaml
Copy code

---

## 📣 License

**MIT License** — free for personal and commercial use.  
Please credit or star the repo if you find it helpful.

---

## 🤝 Contributing

Pull requests welcome!  
To add a new workflow:
- Follow the naming pattern: `Source_to_Target_Feature-Highlights.json`
- Include a brief “What it does” section in this README.

---

## ⚠️ Disclaimer

These automations interact with third-party APIs.  
Use responsibly, comply with each platform’s terms, and test thoroughly before production.