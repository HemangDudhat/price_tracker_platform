# 📉 DealDrop – Smart Price Tracking Platform

DealDrop is a smart price tracking web platform that allows users to monitor product prices, visualize historical price trends, and receive instant email alerts when a price drop is detected. It helps users make informed purchasing decisions by automating price monitoring and notifications.

---

## 🚀 Features

- 🔐 Google Authentication using Supabase
- 🔗 Add products using product URLs
- 🕷️ Automated product price crawling via FireCrawl
- ⏰ Daily price checks using Supabase Cron Jobs
- 📉 Automatic price drop detection
- 📬 Email alerts using MailerSend
- 📊 Interactive price history charts using Recharts
- 📱 Responsive and user-friendly UI

---

---

## 🛠 Tech Stack

### Framework
- **Next.js** – Full-stack framework (Frontend + Backend)

### Database & Authentication
- **Supabase**
  - PostgreSQL database
  - Google OAuth authentication
  - Row level Security (RLS)
  - Built-in cron jobs

### Web Crawling
- **FireCrawl**
  - Extracts product details and pricing data from URLs

### Charts & Visualization
- **Recharts**
  - Interactive price history line charts

### Email Service
- **MailerSend**
  - Sends automated price drop alerts

### Deployment
- **Vercel**

---

## 🧠 Application Flow

1. User signs in using **Google Authentication**
2. User adds a product by submitting its **product URL**
3. Product details and initial price are fetched using **FireCrawl**
4. Product data is stored in **Supabase**
5. **Supabase Cron Job** runs daily:
   - Crawls product pages
   - Stores new price entries
   - Compares old and new prices
6. Price history is visualized using **Recharts**
7. If a **price drop is detected**, an email alert is sent via **MailerSend**


---

## 📋 Prerequisites

### Before you begin, ensure you have:

- Node.js 18+ installed
- A [Supabase](https://supabase.com/) account
- A [Firecrawl](https://www.firecrawl.dev/) account
- A [Mailersend](https://app.mailersend.com/) account
- Google OAuth credentials from [Google Cloud Console](https://console.cloud.google.com/apis/credentials)

---

## Environment variables

```
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Firecrawl
FIRECRAWL_API_KEY=your_firecrawl_api_key

# MailerSend
MAILERSEND_API_KEY=your_mailersend_api_key
MAILERSEND_FROM_EMAIL=your_verified_sender_email

# Cron Job Security (generate with: node -e "console.log(require('crypto').randomBytes(32).toString('hex'))")
CRON_SECRET=your_generated_cron_secret

# App URL
NEXT_PUBLIC_APP_URL=http://localhost:3000
```