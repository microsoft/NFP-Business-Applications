# 🏷️ AI Pricing Lookup Tool for Clothing
This solution showcases how Power Platform can be used to automate pricing lookup and item cataloging for donated clothing. It combines AI Builder, Power Apps, Dataverse, and Power Automate to streamline intake workflows, enhance pricing consistency, and demonstrate extensible capabilities for nonprofit or retail scenarios.

![image](/assets/PP-AI-Pricing-Tool.png)


# 📦 Contents
1. [AI_Pricing_Tool_1_0_0_1.zip](/Power-Platform/Solution-Accelerators/AI-Pricing-Tool/AI_Pricing_Tool_1_0_0_1.zip): This .zip file is packaged solution that will be imported for installation. Download this .zip file in preparation for installation. **You do not need to unzip the file.**
2. [solution-overview.md](/Power-Platform/Solution-Accelerators/AI-Pricing-Tool/solution-overview.md): This markdown contains important information about the solution. **Please read this file before installing.**
3. [installation-guide.md](Power-Platform/Solution-Accelerators/AI-Pricing-Tool/installation-guide.md): This markdown contains step-by-step instructions to install the solution in your own environment.
4. Assets: This folder contains images used throughout the markdown files.

# 💳 Licensing Requirements
This solution is built on the Microsoft Power Platform, and leverages Power Apps, Dataverse, AI Builder, and Power Automate. 

**Please reach out to our team [here](https://forms.office.com/r/thbycKHAnA) if you would like to purchase licensing to use this solution.** 

**Visit [Microsoft for Nonprofit](https://www.microsoft.com/en-us/nonprofits/dynamics-365) for information about our nonprofit offers and discounting.**

| **Capability**                  | **License Requirement**                                                                                                                                |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Power Apps Canvas App           | ✔ [Power Apps Premium](https://www.microsoft.com/en-us/power-platform/products/power-apps/pricing?msockid=1bfb110773b5613b1fc305fa72b26073) (recommended for cross-product and Dataverse integration) |
| Dataverse                       | ✔ Included with Power Apps license when used as the data platform                                                                                      |
| AI Builder (GPT-4o model usage) | ✔ [AI Builder credits](https://learn.microsoft.com/en-us/ai-builder/credit-management) (separate purchase may be required)                                             |
| Power Automate Cloud Flows      | ✔ [Power Automate Premium](https://www.microsoft.com/en-us/power-platform/products/power-automate/pricing?msockid=1bfb110773b5613b1fc305fa72b26073) or Process license                                                      |
## AI Builder credits ##
The following guidance is based on AI Builder licensing rates as of May 2025. Please consult the [Power Platform Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130) for the latest pricing information.

  - AI Builder is licensed based on monthly capacity via the AI Builder capacity add-on. Usage is measured in **service credits**.
  - The Clothing Price Lookup model, as provided, consumes **59 credits per run**.
  - Because image quality or tagging may result in an invalid or incomplete response, we recommend budgeting for **two runs per textile**, allowing for a retry.
  - To estimate your required capacity: **Monthly Credits Needed = Textiles per Month × 118 credits** (i.e., 59 credits × 2 runs).
  - **Example**: If an organization processes 100,000 textiles per month:  
    `100,000 × 118 = 11,800,000 credits/month`

### 💳 AI Builder Capacity Pack Options (as of May 2025) ###
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

   
# ⚠️ Disclaimer 
*This solution is provided as a Power Platform accelerator to help organizations explore, test, and customize AI-driven clothing pricing workflows for their own internal scenarios. It is **not a production-ready solution** and is intended solely for demonstration and proof-of-concept purposes.*

*Microsoft makes no warranties, express or implied, with respect to the solution. **Use of this solution is at your own risk.** Microsoft does not assume any responsibility or liability for any direct or indirect issues that may arise from its deployment or use, including but not limited to data integrity, AI accuracy, pricing estimates, or security compliance.*

*Organizations are solely responsible for evaluating, testing, securing, and modifying the solution to meet their specific requirements before any production use.*
