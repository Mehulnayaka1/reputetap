# ReputeTap NFC Programming Standard Operating Procedure (SOP)

## Required Equipment & Tools
1. **Programming Device**: Smartphone equipped with NFC (iPhone XS/11/12/13/14/15/16/17 or any Android with NFC enabled).
2. **Mobile Application**: **NFC Tools** (Free on Google Play Store & Apple App Store).
3. **Hardware Target**: Blank NTAG213 (144 bytes) or NTAG215 (504 bytes) 25mm adhesive tags / embedded acrylic standees.

---

## 5-Step Programming Walkthrough (< 20 Seconds Per Standee)

### Step 1: Construct the Client Target URL
Combine the client’s Google Place ID, owner WhatsApp phone number, business name, and venue category into the standardized URL structure:

```url
https://reputetap.pages.dev/?placeid=ChIJN1t_tDeuEmsRUsoyG83frY4&biz=The%20Roasting%20Room&phone=919876543210&type=cafe
```

> **Dynamic Shortlink Recommendation**:
> Use a dynamic short URL (e.g., `reputetap.com/r/client_slug`) that 301-redirects to the parameter URL. This permits updating the client's destination URL or WhatsApp number remotely without re-writing physical standee chips.

---

### Step 2: Configure NFC Tools App
1. Open the **NFC Tools** application on your smartphone.
2. Select **Write** from the primary menu options.
3. Tap **Add a record**.

---

### Step 3: Add URL/URI Record
1. Select **URL / URI** from the record list.
2. Choose `https://` protocol prefix.
3. Paste the client’s ReputeTap URL (e.g., `reputetap.pages.dev/?placeid=...`).
4. Tap **OK** in the top-right corner to save the record payload.

---

### Step 4: Encode the Physical Standee
1. Tap **Write / [payload size] Bytes**.
2. Hold your phone's NFC antenna (top edge on iOS, center-back on Android) against the standee's `(( NFC ))` icon target area.
3. Maintain contact until you hear the confirmation chime and see the green checkmark: **"Write complete!"**

---

### Step 5: Lock Chip Memory (Mandatory for Production)
To prevent unauthorized individuals or public customers from overwriting the standee URL:
1. Test the written standee by tapping it with a secondary phone to verify it opens the correct web app.
2. In **NFC Tools**, navigate to **Other** → **Lock memory**.
3. Hold the phone against the standee tag to permanently lock the chip.
> **Warning**: Memory locking is **irreversible**. Only execute Step 5 after verifying URL functionality.
