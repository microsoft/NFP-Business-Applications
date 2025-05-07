# 🏷️ AI Pricing Lookup Tool for Clothing
This solution showcases how Power Platform can be used to automate pricing lookup and item cataloging for donated clothing. It combines AI Builder, Power Apps, Dataverse, and Power Automate to streamline intake workflows, enhance pricing consistency, and demonstrate extensible capabilities for nonprofit or retail scenarios.

![image](/assets/PP-AI-Pricing-Tool.png)

# ⚠️ Disclaimer
This solution is provided as a Power Platform accelerator to help organizations explore, test, and customize AI-driven clothing pricing workflows for their own internal scenarios. It is **not a production-ready solution** and is intended solely for demonstration and proof-of-concept purposes.
 
Microsoft makes no warranties, express or implied, with respect to the solution. **Use of this solution is at your own risk.** Microsoft does not assume any responsibility or liability for any direct or indirect issues that may arise from its deployment or use, including but not limited to data integrity, AI accuracy, pricing estimates, or security compliance.
 
Organizations are solely responsible for evaluating, testing, securing, and modifying the solution to meet their specific requirements before any production use.


## 📎 Components

| **Display Name**                          | **Type**             | **Purpose**                                                                                         |
|-------------------------------------------|----------------------|------------------------------------------------------------------------------------------------------|
| Clothing Price Check                      | AI Model             | Identifies brands, describes items, and estimates resale value using GPT-4o                         |
| Clothing Price Lookup                     | Canvas App           | Provides UI for image capture, condition input, AI execution, result review, and barcode triggering |
| Clothing Price Lookup - Barcode Generator | Cloud Flow           | Triggers saving to Dataverse and barcode generation (color logic is handled in-app only)            |
| Clothing Price Lookup - Dataverse         | Connection Reference | Connects the app and flows to Dataverse                                                             |
| DonatedGoods                              | Dataverse Table      | Stores item data including brand, description, price, and barcode                                   |
| Houseware Price Check (optional)          | AI Model             | Optional extension for non-clothing items                                                           |


## 🧠 AI Capabilities

The solution includes a GPT-4o-based AI Builder model called **Clothing Price Check**, which uses generative AI to assess and price clothing based on tag data, condition, and resale market trends.

### 🤖 Key Features

- **Brand Identification** — Detects the brand from the image input. If unidentifiable, outputs `"Brand not identified"` and prompts the user to tag a photo of the items tag.
- **Description Generation** — Produces an item description using AI analysis of the image and metadata.
- **Price Estimation** — Returns a realistic resale price range based on data from platforms like Poshmark, eBay, and ShopGoodwill.
- **Price Justification** — Provides reasoning behind the price range based on item condition, demand, and market trends.
- **Fabric Composition Guess** — Estimates the item’s material breakdown. Notes uncertainty if image input is unclear.

The model is executed with three parameters: the item image, manually entered condition, and the current year. This approach demonstrates how AI Builder can support both automated and user-defined logic.

### 🧾 Example Output

```json
{
  "brand": "Nike",
  "description": "This is a navy blue Nike t-shirt with a prominent 'NIKE' logo in white and blue on the front. The shirt appears to be in good condition, with no visible signs of wear or damage.",
  "condition": "Good",
  "retail_price": 45,
  "price_range": {
    "min_price": 15,
    "max_price": 25
  },
  "price_justification": "The price range is based on the current market for used Nike t-shirts in good condition. Nike is a well-known and popular brand, and their t-shirts typically retain value well in the resale market. The condition of the shirt being good, with no visible wear and the logo being intact, supports this price range. Additionally, the presence of the tag suggests it may be new or barely used, which can slightly increase its resale value.",
  "recycling_content": "Polyester 50%, Cotton 50%"
}
```

## 🚀 How It Works

1. **Capture** — The user captures or uploads an image of a donated clothing item within the Power App.
2. **Enter Condition** — The app prompts the user to manually enter the item's condition. This supports customization for different intake workflows.
3. **Run Price Search** — Clicking the **Run Price Search** button executes the AI Builder model using the image, condition, and current year (autopopulated).
4. **Review Results** — The app displays AI-generated brand, description, resale price range, retail price, recycling content, and justification.
5. **Override Values** — A **Generate Barcode** button becomes visible. The user may override the brand, description, resale price (defaulted to the average), and retail price.
6. **Save & Tag** — When the user clicks **Generate Barcode**, a background Power Automate flow saves the item to the `DonatedGoods` table and generates a barcode.
   - The barcode is color-coded based on a rolling 5-week logic handled within the app. This supports point-of-sale discounting policies, such as 20% off for items older than 5 weeks. The logic is configurable per organization.
7. **Store** — The item record is saved in Dataverse, ready for inventory tracking, reporting, or downstream workflows.
8. **E-Commerce Integration (Optional)** — A non-functional **Post to eBay** button illustrates future extensibility for online resale integration.


## 💡 Use Case Scenarios

This accelerator demonstrates:

- AI-powered intake workflows for nonprofit or thrift organizations
- Manual parameter entry to support customizable pricing rules
- Barcode-based inventory tagging and discount scheduling
- Recycling content capture to support item sorting and eco-friendly disposal
- Integration across Power Apps, AI Builder, Power Automate, and Dataverse


## 🛠️ Prerequisites

To deploy and use this solution, your environment must meet the following requirements:

### ✅ Environment Setup

- A **Microsoft Power Platform environment** with **Dataverse** enabled
- Access to the **Power Platform** to import and configure solution components

### 💳 Licensing Requirements
This solution is built on the Microsoft Power Platform, and leverages Power Apps, Dataverse, AI Builder, and Power Automate. 

**Please reach out to our team [here](https://forms.office.com/r/thbycKHAnA) if you would like to purchase licensing to use this solution.** 

**Visit [Microsoft for Nonprofit](https://www.microsoft.com/en-us/nonprofits/dynamics-365) for information about our nonprofit offers and discounting.**

| **Capability**                  | **License Requirement**                                                                                                                                |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Power Apps Canvas App           | ✔ [Power Apps Premium](https://www.microsoft.com/en-us/power-platform/products/power-apps/pricing?msockid=1bfb110773b5613b1fc305fa72b26073) (recommended for cross-product and Dataverse integration) |
| Dataverse                       | ✔ Included with Power Apps license when used as the data platform                                                                                      |
| AI Builder (GPT-4o model usage) | ✔ [AI Builder credits](https://learn.microsoft.com/en-us/ai-builder/credit-management) (separate purchase may be required)                                             |
| Power Automate Cloud Flows      | ✔ [Power Automate Premium](https://www.microsoft.com/en-us/power-platform/products/power-automate/pricing?msockid=1bfb110773b5613b1fc305fa72b26073) or Process license                                                      |
#### AI Builder credits ####
The following guidance is based on AI Builder licensing rates as of May 2025. Please consult the [Power Platform Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130) for the latest pricing information.

  - AI Builder is licensed based on monthly capacity via the AI Builder capacity add-on. Usage is measured in **service credits**.
  - The Clothing Price Lookup model, as provided, consumes **59 credits per run**.
  - Because image quality or tagging may result in an invalid or incomplete response, we recommend budgeting for **two runs per textile**, allowing for a retry.
  - To estimate your required capacity: **Monthly Credits Needed = Textiles per Month × 118 credits** (i.e., 59 credits × 2 runs).
  - **Example**: If an organization processes 100,000 textiles per month:  
    `100,000 × 118 = 11,800,000 credits/month`

##### 💳 AI Builder Capacity Pack Options (as of May 2025) #####
Please consult the [Power Platform Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130) for the latest licensing information. 
**Visit [Microsoft for Nonprofit](https://www.microsoft.com/en-us/nonprofits/dynamics-365) for information about our nonprofit offers and discounting.**

| **Capacity Pack Tiers** | **AI Builder add-on SKU Names**        | **Minimum Purchase** | 
|--------------------------|----------------------------------------|------------------------|
| Tier 1                  | AI Builder Capacity T1 add-on          | 1 capacity pack        |
| Tier 2                  | AI Builder Capacity T2 add-on          | 10 capacity packs      |
| Tier 3                  | AI Builder Capacity T3 add-on          | 50 capacity packs      |

- 📌 *Each pack includes **1 million service credits** per month.
- ⚠️ AI Builder credits are not included in Power Apps Developer environments by default.
- *Service credits are used across Power Automate, Power Apps, and Dynamics 365 AI Builder models.
- *Credits apply to both training and production use.
- For AI Builder capacity add-on SKUs, purchased capacity is enforced monthly and unused service credits do not carry over month to month.

### 🔗 Permissions & Connectors

- Assign appropriate Dataverse roles (e.g., **System Customizer**)
- For optional scraping or e-commerce extensions, **custom connectors** or **premium connectors** may be required

## Submit feedback

Let us know by filing an issue. 
Before submitting your issue please search the [issues](https://github.com/microsoft/TSI-Business-Applications/issues) to ensure your issue has not already been reported

If your bug or feature request has already been reported, join the conversation by commenting and adding your reaction. Please use reactions to vote and not "+1" comments.
- 👍: upvote
- 👎: downvote

