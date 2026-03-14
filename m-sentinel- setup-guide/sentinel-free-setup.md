# Microsoft Sentinel Free Lab Setup Guide

A step-by-step guide to setting up a free Microsoft Sentinel workspace for practising KQL detection rules and SIEM operations.

---

## Cost

Microsoft Sentinel offers a **free trial** with:
- First 31 days free on a new Log Analytics workspace
- 10 GB/day free data ingestion during trial
- Free Azure account gives $200 credit for new users

**After trial:** Pay-as-you-go or use minimal free data sources to keep costs near zero.

---

## Step 1 — Create Azure Free Account

1. Go to https://azure.microsoft.com/free
2. Sign up with Microsoft account
3. Verify with credit card (not charged during free tier)
4. You will receive $200 credit valid for 30 days

---

## Step 2 — Create Log Analytics Workspace

1. In Azure Portal search for **Log Analytics Workspaces**
2. Click **Create**
3. Settings:
   - Subscription: Your free subscription
   - Resource Group: Create new → name it `soc-lab-rg`
   - Name: `soc-lab-workspace`
   - Region: Choose nearest to you
4. Click **Review + Create** → **Create**

---

## Step 3 — Enable Microsoft Sentinel

1. Search for **Microsoft Sentinel** in Azure Portal
2. Click **Create Microsoft Sentinel**
3. Select the workspace you just created
4. Click **Add**

Sentinel is now active on your workspace.

---

## Step 4 — Connect Free Data Sources

Go to **Sentinel → Data Connectors** and enable:

### Option 1 — Azure Activity Logs (Free)
- Connects Azure subscription activity
- Shows resource creation, deletion, policy changes
- Good for practicing cloud security detection

### Option 2 — Microsoft Defender for Cloud (Free tier)
- Security recommendations and alerts
- Good for vulnerability management practice

### Option 3 — Windows Security Events (if you have a VM)
- Create a free Azure VM (B1s — free for 12 months)
- Install the Log Analytics agent
- Stream Windows Security Events to Sentinel

---

## Step 5 — Run Your First KQL Query

In Sentinel go to **Logs** and try:

```kql
// Check what data is coming in
union *
| summarize count() by Type
| sort by count_ desc
```

```kql
// View recent Azure activity
AzureActivity
| where TimeGenerated > ago(24h)
| project TimeGenerated, Caller, OperationNameValue, ActivityStatusValue
| sort by TimeGenerated desc
```

---

## Step 6 — Create Your First Analytics Rule

1. Go to **Sentinel → Analytics**
2. Click **Create → Scheduled query rule**
3. Paste any KQL from the `detection-rules/` folder
4. Set frequency and lookback period
5. Configure alert details and severity
6. Save and enable

---

## Keeping Costs Low

- Delete the VM when not using it
- Set a daily data cap on Log Analytics workspace
- Use free data connectors only
- Monitor costs in **Azure Cost Management**

---

## Next Steps After Setup

- [ ] Run all queries in `hunting-queries/` folder
- [ ] Create analytics rules from `detection-rules/` folder
- [ ] Practice the IR workflow in `playbooks/` folder
- [ ] Build a Workbook dashboard for monitoring

---

*This guide documents the setup process for reference — lab queries are currently tested in MDE Advanced Hunting with plans to deploy to Sentinel free tier.*
