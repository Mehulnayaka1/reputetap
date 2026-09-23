# ReputeTap Automated Negative Feedback Notification Webhook Guide

## System Overview
When a customer submits private negative feedback on the ReputeTap micro-landing page (`index.html`), the application simultaneously dispatches:
1. **Client-Side WhatsApp Deep-Link**: Opens a pre-formatted WhatsApp chat (`wa.me/{owner_phone}?text=...`) directly to the owner/manager.
2. **Automated Background HTTP POST Webhook**: Dispatches a structured JSON payload to any external webhook URL passed via `?webhook=https://...`.

---

## Webhook JSON Payload Schema

```json
{
  "business": "The Roasted Bean Cafe",
  "placeId": "ChIJN1t_tDeuEmsRUsoyG83frY4",
  "stars": 2,
  "customerName": "Rahul Sharma",
  "customerPhone": "+919876543210",
  "comment": "Waited 35 minutes for our drinks and the table was dirty.",
  "timestamp": "2026-09-23T09:40:00.000Z"
}
```

---

## Recommended Integration Options

### Option 1: n8n / Make.com Automation Workflow (Recommended for Agencies)
- **Trigger**: Webhook listener endpoint receiving the ReputeTap JSON POST.
- **Action 1 (Telegram Bot)**: Send instant Telegram notification to venue manager group:
  > 🚨 **ReputeTap Complaint Alert**  
  > **Venue**: The Roasted Bean Cafe  
  > **Customer**: Rahul Sharma (`+919876543210`)  
  > **Rating**: 2 / 5 Stars  
  > **Comment**: *"Waited 35 minutes for drinks..."*  
  > [Tap to Call Customer](tel:+919876543210)
- **Action 2 (WhatsApp Cloud API)**: Send automated WhatsApp template alert directly to manager handset.

---

### Option 2: Formspree / Formbold Endpoint (Zero-Code Setup)
1. Register a free account on [Formspree](https://formspree.io) or [Formbold](https://formbold.com).
2. Create a form endpoint and append it to the client URL:
   `?webhook=https://formspree.io/f/xayzvbwn`
3. Formspree instantly delivers an email notification to the manager with one-tap telephone dial links whenever a complaint is submitted.

---

### Option 3: Custom Node.js / Python Webhook Handler
Below is an example minimal Express.js endpoint to log complaints and send SMS alerts via Twilio/Fast2SMS:

```javascript
const express = require('express');
const app = express();
app.use(express.json());

app.post('/api/reputetap-webhook', (req, res) => {
  const { business, stars, customerName, customerPhone, comment, timestamp } = req.body;
  
  console.log(`[ALERT] ${stars}-star feedback for ${business} from ${customerName} (${customerPhone})`);
  console.log(`Comment: ${comment}`);

  // Insert database logging or SMS gateway logic here

  res.status(200).json({ success: true, message: 'Feedback logged successfully' });
});

app.listen(3000, () => console.log('ReputeTap Webhook Server listening on port 3000'));
```
