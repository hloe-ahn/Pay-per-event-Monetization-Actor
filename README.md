# Pay-per-event Monetization Actor
>This Actor demonstrates how to implement the pay-per-event billing model on the Apify platform. It shows how you can charge users for specific events (like starting a run or producing a result) rather than for resource usage or number of results — giving you more predictable and flexible monetization. Ideal as a template for building your own paid Actors.

<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>

<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>Pay-per-event Monetization Actor</strong> you've just found your team — Let's Chat. 👆👆
</p>

## Introduction
The Pay-per-event Monetization Actor provides a ready-made example for developers who want to monetize their Apify Actors with fine-grained billing. Instead of paying by result count or usage, this model bills per event, giving more transparent pricing for users and control for developers. Works with both JavaScript and Python SDKs (or via API/HTTP).

### Why It’s Useful
- Lets you charge per discrete events (Actor start, result creation, etc.), not just per result or runtime.  
- More predictable billing for users and easier cost control.  
- Acts as a reference implementation when you build your own monetized Actor.  
- Integrates seamlessly with Apify’s billing, dataset output, and SDK support.  

---
## Features
| Feature | Description |
|---------|-------------|
| Event-based billing | Charges only for configured events (e.g. Actor start or item output) instead of usage volume. |
| SDK & API support | Works with JavaScript, Python, HTTP API; can be called programmatically. |
| Dataset integration | Outputs data via standard datasets while charging for event occurrences. |
| Cost cap support | Stops execution gracefully once user-specified cost limit is reached. |
| Example code | Reference implementation showing how to use `Actor.charge()` / `ChargingManager` in code. |

---
## What Data / Behavior This Actor Handles
| Field / Behavior | Description |
|-----------------|-------------|
| event_name='init' | Charges when the Actor run starts. |
| event_name='result-item' | Charges when a single result/item is pushed to dataset. |
| count parameter | Allows charging per item (e.g. for multiple results in a single run). |
| maxTotalChargeUsd | Optional cap to limit maximum charge per run. |
| Dataset output | Stores data items as normal — billing is separate from result generation. |

---
## Example Usage (Python SDK)
    
    import asyncio
    from apify import Actor
    
    async def main():
      async with Actor:
        await Actor.charge(event_name='init')  # charge for run start
        result = [{'word': 'Hello'}, {'word': 'World'}]
        await Actor.push_data(result, 'result-item')  # charges per item

    if __name__ == '__main__':
      asyncio.run(main())

You can also run via API or JavaScript — refer to documentation and choose whatever integration fits your workflow.

---
## Directory Structure Tree
    
    pay-per-event-monetization/
    ├── src/
    │   ├── main.js      # or main.py for Python variant
    │   ├── charge_manager.js  # helper for event billing
    │   └── config/
    │       └── actor.json  # billing/event configuration
    ├── package.json or requirements.txt
    └── README.md

---
## Use Cases
- **You** build a new scraper and want to monetize per user action (not per result) — this Actor shows how.  
- **Teams** offering API-like services — you can charge per call / per data extraction event.  
- **Freelancers** providing on-demand automation, billing clients precisely for tasks done.  
- **SaaS build-ups** where you need predictable, event-based billing for usage.  

---
## FAQs

**What does “event” mean here?**  
An event is a code-triggered action (e.g. run start, dataset item output, or a custom action) that you define for billing.

**Do I pay for platform usage or results?**  
No — you pay only for the defined events. Platform usage costs are handled separately by Apify infrastructure.

**Can I cap the amount I pay per run?**  
Yes — you can set `maxTotalChargeUsd` when running the Actor to limit costs.

**Which SDKs are supported?**  
JavaScript, Python, HTTP API — all supported.  

---
### Performance & Revenue Mechanics

**Billing Logic:**  
Charges per event as defined (e.g. run start = $X, each result item = $Y). User sets cost cap per run.  

**Developer Earnings:**  
You receive 80% of revenue (after platform costs and Apify fees) when users run the Actor under paid plans. :contentReference[oaicite:0]{index=0}

**Use Cases for PPE Model:**  
Ideal for services with complex workflows or variable output — allows precise, event-based charging instead of per-result or flat-usage billing. :contentReference[oaicite:1]{index=1}





---


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
         </p>
