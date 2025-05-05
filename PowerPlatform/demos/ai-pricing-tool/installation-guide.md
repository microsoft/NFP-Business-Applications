# 🛠️ Installation Guide: AI Pricing Lookup Tool for Clothing

This guide walks you through the steps required to install and configure the AI Pricing Lookup solution within your Power Platform environment.

> ⚠️ This solution is intended for demonstration purposes only. Please review the [solution-overview.md](/PowerPlatform/demos/ai-pricing-tool/solution-overview.md) before deploying.


## ✅ Prerequisites

Before you begin, ensure the following:

- You have access to a Microsoft Power Platform environment with **Dataverse** enabled.
  - A dedicated environment is recommended for this deployment.
  - See [Environments](https://learn.microsoft.com/en-us/power-platform/admin/environments-overview) documentation.
- You are assigned the **Environment Maker** role.
- You have **Power Apps Premium** or equivalent licenses.
- You have sufficient **AI Builder credits** available.
  - See [LicensingCalculator.xlsx](/licensingcalculator.xlsx)


## 📦 Solution Contents

The solution package includes:

- Canvas App: `Clothing Price Lookup`
- AI Model: `Clothing Price Check`
- Power Automate Flow: `Barcode Generator`
- Dataverse Table: `DonatedGoods`
- Connection Reference: `Dataverse`


## 📥 Step-by-Step Installation

### 1. **Import the Solution**

1. Go to [Power Apps Maker Portal](https://make.powerapps.com/).
2. In the top right, ensure you have selected the environment you wish to deploy the solution to. See [Prerequisites](#-prerequisites)
3. In the left menu, select **Solutions**.
4. Click **Import solution**.
5. Upload the provided `.zip` solution file.
6. Click **Next**, review dependencies, and then **Import**.

### 2. **Verify AI Builder Licensing**

- Navigate to [AI Builder > Models](https://make.powerapps.com/aiBuilder/models).
- Ensure the **Clothing Price Check** model is listed and successfully published.
- Confirm AI Builder credits are available in your tenant.

### 3. **Configure Connections**

- During import, ensure that the **Dataverse** connection reference is mapped correctly.
- After import, open the flow named `Barcode Generator` and reauthenticate if needed.

### 4. **Publish the Canvas App**

1. Go to **Apps** in the Maker Portal.
2. Open `Clothing Price Lookup`.
3. Click **Edit**, verify configuration, then **Publish**.


## ⚙️ Post-Installation Tasks

- **AI Model Testing**: Open the app, capture an image, and test the **Run Price Search** button.
- **Barcode Flow**: Verify that clicking **Generate Barcode** triggers the flow and creates a Dataverse record.
- **Color Coding Logic**: Color tag display is handled in-app only and does not write to Dataverse.
- **Manual Overrides**: Try overriding brand, description, and pricing in the app before saving.


## 🚫 Known Limitations

- Barcode color tag is not stored in Dataverse (display-only).
- “Post to eBay” button is illustrative only and does not perform any action.
- The pricing model is a demonstration and should be validated against real-world data before production use.


## Submit feedback

Let us know by filing an issue.  

Before submitting your issue please search the [issues](https://github.com/microsoft/TSI-Business-Applications/issues) to ensure your issue has not already been reported.

If your bug or feature request has already been reported, join the conversation by commenting and adding your reaction. Please use reactions to vote and not "+1" comments.

- 👍: upvote  
- 👎: downvote  

---
