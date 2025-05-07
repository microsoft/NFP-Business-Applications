# 🛠️ Installation Guide: AI Pricing Lookup Tool for Clothing

This guide walks you through the steps required to install and configure the AI Pricing Lookup solution within your Power Platform environment.

> ⚠️ This solution is intended for demonstration purposes only. Please review the [solution-overview.md](/PowerPlatform/demos/ai-pricing-tool/solution-overview.md) before deploying.


## ✅ Prerequisites

Before you begin, ensure the following:

- You have access to a Microsoft Power Platform environment with **Dataverse** enabled.
  - A dedicated environment is recommended for this deployment.
  - See [Environments](https://learn.microsoft.com/en-us/power-platform/admin/environments-overview) documentation.
- You are assigned the **System Customizer** role in the environment.
- You have **Power Apps Premium** or equivalent licenses.
- You have sufficient **AI Builder credits** available. The following guidance is based on AI Builder licensing rates as of May 2025. Please consult the [Power Platform Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130) for the latest pricing information.

  - AI Builder is licensed based on monthly capacity via the AI Builder capacity add-on. Usage is measured in **service credits**.
  - The Clothing Price Lookup model, as provided, consumes **59 credits per run**.
  - Because image quality or tagging may result in an invalid or incomplete response, we recommend budgeting for **two runs per textile**, allowing for a retry.
  - To estimate your required capacity: **Monthly Credits Needed = Textiles per Month × 118 credits** (i.e., 59 credits × 2 runs).
  - **Example**: If an organization processes 100,000 textiles per month:  
    `100,000 × 118 = 11,800,000 credits/month`

### 💳 AI Builder Capacity Pack Pricing (as of May 2025)
Please consult the [Power Platform Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130) for the latest licensing information. 
**Visit [Microsoft for Nonprofit](https://www.microsoft.com/en-us/nonprofits/dynamics-365) for information about our nonprofit offers and discounting.**

| **Capacity Pack Tiers** | **AI Builder add-on SKU Names**        | **Minimum Purchase** | 
|--------------------------|----------------------------------------|------------------------|
| Tier 1                  | AI Builder Capacity T1 add-on          | 1 capacity pack        |
| Tier 2                  | AI Builder Capacity T2 add-on          | 10 capacity packs      |
| Tier 3                  | AI Builder Capacity T3 add-on          | 50 capacity packs      |

> 📌 *Each pack includes **1 million service credits** per month.  
> *Service credits are used across Power Automate, Power Apps, and Dynamics 365 AI Builder models.  
> *Credits apply to both training and production use.
> For AI Builder capacity add-on SKUs, purchased capacity is enforced monthly and unused service credits do not carry over month to month.

**Please reach out to our team [here](https://forms.office.com/r/thbycKHAnA) if you would like to purchase licensing to use this solution.** 

**Visit [Microsoft for Nonprofit](https://www.microsoft.com/en-us/nonprofits/dynamics-365) for information about our nonprofit offers and discounting.**

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
7. The solution may take a few minutes to import. You will see a green banner along the top of the Solution explorer screen that says, `Solution "AI Pricing Tool" imported successfully.` once the installation is complete. 

### 2. **Verify AI Builder Licensing**

- After import, navigate to [AI Builder > Models](https://make.powerapps.com/aiBuilder/models).
  - Double-check that you have selected the environment you installed the solution in.
- Select the tile that says **Prompts now have their own section**
- Ensure the **Clothing Price Check** model is listed under **My Prompts** with a Status of `Published`.
- Confirm AI Builder credits are available in your tenant.
  - See [AI Builder Credit Management](https://learn.microsoft.com/en-us/ai-builder/credit-management)

### 3. **Configure Connections**

- During import, ensure that the **Dataverse** connection reference is mapped correctly.
- After import, in the left menu, navigate to **Solutions**.
- Select the **AI Pricing Tool** solution
- Select and open the flow named `Clothing Price Lookup | Barcode Generator` and reauthenticate if needed.

### 4. **Publish All Customizations**

- After import, in the left menu, navigate to **Solutions**.
- In the top ribbon, select **Publish All Customizations**.


## ⚙️ Post-Installation Tasks

- **AI Model Testing**: Open the `Clothing Price Lookup` app, capture or upload an image, and test the **Run Price Search** button.
  - For best results:
    - Ensure the image is taken in a well-lit area to capture clear details
    - Ensure the entire item is visible in the frame
    - Place the item against a plain background for better focus
    - Include any notable markings, logos or branding to help the system identify the item
- **Barcode Flow**: Verify that clicking **Generate Barcode** triggers the flow and creates a Dataverse record.
- **Color Coding Logic**: Verify when a barcode is generated, the app reveals a color-coded tag. Note that color tag display is handled in-app only and does not write to Dataverse. 
- **Manual Overrides**: Try overriding brand, description, and pricing in the app before saving.


## 🚫 Known Limitations

- Barcode color tag is not stored in Dataverse (in-app display-only).
- “Post to eBay” button is illustrative only and does not perform any action.
- The pricing model is a demonstration and should be validated against real-world data before production use.


## Submit feedback

Let us know by filing an issue.  

Before submitting your issue please search the [issues](https://github.com/microsoft/TSI-Business-Applications/issues) to ensure your issue has not already been reported.

If your bug or feature request has already been reported, join the conversation by commenting and adding your reaction. Please use reactions to vote and not "+1" comments.

- 👍: upvote  
- 👎: downvote  

---
