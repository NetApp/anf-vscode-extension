# Azure NetApp Files VS Code Extension

**AI-Powered Storage Management for Developers**

A VS Code extension that brings Azure NetApp Files (ANF) storage management directly into your development environment. Manage storage resources, generate templates, and get AI-powered recommendations without leaving VS Code.

[![VS Code Marketplace](https://img.shields.io/badge/VS%20Code-Marketplace-blue)](https://marketplace.visualstudio.com/items?itemName=netapp.anf-vscode-extension)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-1.2.0-orange)](package.json)


**The Solution:** AI-powered storage management integrated directly into VS Code with natural language commands and intelligent recommendations.

## ✨ Key Features

### AI-Powered Chat Integration
- **@anf Chat Participant:** Natural language storage management through GitHub Copilot
- **Intelligent Recommendations:** AI-powered analysis and optimization suggestions
- **Context-Aware Assistance:** Framework-specific code generation and best practices

### Core Functionality
- **Resource Management:** Browse and manage ANF accounts, capacity pools, and volumes
- **Template Generation:** Create ARM, Terraform, and Powershell templates with AI assistance
- **One-Click Operations:** Copy connection strings, generate mount scripts, and deploy templates
- **Real-Time Analysis:** Performance metrics and cost optimization insights

### Developer/Devops Experience
- **Zero Context Switching:** Everything happens in VS Code
- **Natural Language Commands:** "analyze this volume", "generate ARM template", "optimize configuration"
- **Framework Integration:** Direct code insertion for .NET, Python, Java, Node.js

## Prerequisites

- **VS Code:** Version 1.105.0 or higher
- **Azure Account:** With access to Azure NetApp Files
- **Azure Subscription:** With ANF service enabled
- **Permissions:** Contributor or NetApp Contributor role on target subscriptions
- **GitHub Copilot:** For AI-powered chat features (optional but recommended)

## Installation

### From VS Code Marketplace
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for "Azure NetApp Files"
4. Click Install

### From Source
```bash
git clone https://github.com/NetApp/anf-vscode-extension.git
cd anf-vscode-extension
npm install
npm run compile
```

## Quick Start

### 1. Authentication
```bash
# Sign in to Azure
Ctrl+Shift+P → "Azure NetApp Files: Sign in to Azure"

# Select subscription
Ctrl+Shift+P → "Azure NetApp Files: Select Subscription"
```

### 2. Explore Resources
- Open **ANF Explorer** in the sidebar
- Browse your accounts, pools, and volumes
- Right-click items for context actions

### 3. Try AI Features
Open GitHub Copilot chat and try:
- `"@anf analyze this volume"`
- `"@anf generate ARM template for this setup"`


## Natural Language Commands

Transform complex storage management into simple conversations:

| Command                      | Description                                 | Example                                                    |
| ---------------------------- | ------------------------------------------- | ---------------------------------------------------------- |
| `@anf analyze this volume`   | Get AI-powered analysis and recommendations | Analyzes performance, cost, and optimization opportunities |
| `@anf generate ARM template` | Create deployment templates                 | Generates production-ready ARM templates                   |
| `@anf what is this volume`   | Get detailed resource information           | Provides comprehensive resource details                    |

### Volume Management
| Command | Description |
|---------|-------------|
| `@anf create a snapshot for this volume` | Create a new snapshot of the selected volume |
| `@anf list all snapshots` | Display all snapshots for the selected volume |
| `@anf restore from snapshot` | Restore a volume from a snapshot |
| `@anf delete snapshot` | Remove a specific snapshot |
| `@anf set quota limit to 500GB` | Configure volume quota limits |
| `@anf configure export policy` | Set up NFS export policies and rules |
| `@anf show mount target info` | Get mount target details and configuration |
| `@anf monitor performance` | View performance metrics (IOPS, throughput, latency) |

### Cross-Region Replication
| Command | Description |
|---------|-------------|
| `@anf replicate this volume to East US` | Set up cross-region replication to a target region |
| `@anf check replication status` | Display current replication state and health |
| `@anf failover replication to secondary` | Initiate disaster recovery failover |
| `@anf resync replication` | Re-establish replication after failover |

### Backup & Recovery
| Command | Description |
|---------|-------------|
| `@anf create a backup policy` | Set up automated backup schedules |
| `@anf take a manual backup` | Create an immediate backup of the volume |
| `@anf list all backups` | Show available backups and policies |
| `@anf restore from backup` | Recover data from a backup |
| `@anf create backup vault` | Set up a new backup vault |
| `@anf assign volume to backup vault` | Link a volume to a backup vault |

### Template Generation
| Command | Description |
|---------|-------------|
| `@anf generate an ARM template for a NetApp account` | Create Azure Resource Manager deployment templates |
| `@anf create a Terraform configuration` | Generate Terraform infrastructure-as-code files |
| `@anf show me a volume deployment template` | Get deployment templates for volumes |

### Resource Analysis
| Command | Description |
|---------|-------------|
| `@anf analyze my ANF configuration` | Get AI-powered analysis and recommendations |
| `@anf optimize my volume performance` | Receive performance optimization suggestions |
| `@anf review my capacity pool settings` | Analyze capacity pool configuration |

### Troubleshooting
| Command | Description |
|---------|-------------|
| `@anf my volume isn't mounting` | Get help with mount issues |
| `@anf performance issues with ANF` | Diagnose performance problems |
| `@anf connection problems` | Troubleshoot connectivity issues |

### General
| Command | Description |
|---------|-------------|
| `@anf help` | Display all available commands |
| `@anf getting started with ANF` | Learn ANF basics and first steps |
| `@anf how to select a resource` | Learn how to select resources in the tree view |

**💡 Tip:** Select a volume in the ANF tree view before running volume-specific commands for better context!

## Configuration

### Extension Settings
Access via `File → Preferences → Settings → Extensions → Azure NetApp Files`


### Workspace Configuration
Add to `.vscode/settings.json`:
```json
{
  "anf-extension.defaultServiceLevel": "Premium",
  "anf-extension.refreshInterval": 10,
  "anf-extension.aiAdvisor.enabled": true
}
```

## Troubleshooting

### Common Issues

**"No enabled subscriptions found"**
- Cause: Authenticated to tenant without ANF subscriptions
- Solution: Run `Azure NetApp Files: Select Tenant` and choose correct tenant

**"Authentication failed"**
- Cause: Expired or invalid credentials
- Solution: Run `Azure NetApp Files: Sign in to Azure` to re-authenticate

**"@anf commands not working"**
- Cause: GitHub Copilot not installed or AI features disabled
- Solution: Install GitHub Copilot extension and enable AI features in settings

**Extension not loading**
- Cause: VS Code compatibility or corrupted installation
- Solution: Restart VS Code and reinstall the extension

### Debug Mode
Enable debug logging:
```json
{
  "anf-extension.debug": true,
  "anf-extension.logLevel": "debug"
}
```

## Security

- **Authentication:** Uses VS Code's built-in Microsoft authentication provider
- **Token Storage:** Securely stored in VS Code's global state
- **Permissions:** Requires only necessary Azure permissions
- **Data Privacy:** No ANF data stored locally
- **Enterprise Compliance:** Supports Azure AD conditional access policies


### Manual Testing
1. Install extension in development mode
2. Sign in to Azure with test subscription
3. Test all major features and commands


## 📚 Resources

- **[VS Code Marketplace](https://marketplace.visualstudio.com/)** - Install the extension
- **[Documentation](https://docs.netapp.com)** - Complete user guide
- **[GitHub Repository](https://github.com/NetApp/anf-vscode-extension)** - Source code and issues
- **[Community Forum](https://community.netapp.com)** - Get help and share feedback
- **[NetApp Support](https://support.netapp.com)** - Technical support

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues:** [GitHub Issues](https://github.com/NetApp/anf-vscode-extension/issues)
- **Documentation:** [Azure NetApp Files Docs](https://docs.microsoft.com/en-us/azure/azure-netapp-files/)
- **Community:** [Azure Community Forums](https://docs.microsoft.com/en-us/answers/topics/azure-netapp-files.html)

## 🎉 New Features

### Version 1.2.0
- **Agentic Framework Support**
  - We’ve started adding **Agentic Framework** capabilities to the ANF Extension, beginning with a Volume Scanner. It scans all volumes in a subscription, identifies configuration gaps, and suggests AI-powered optimizations—with an actionable **Yes** button to apply the recommended changes to your infrastructure.
- **More Copilot Commands** - The ANF Extension's Copilot Chat integration now supports creating and modifying many more resources:
  * See [Natural Language Commands](#natural-language-commands)

### Version 1.1.0

- **Multi-Tenant Support:** The ANF Extension now supports logging into more than just your home Tenant!
- **Right-Click Mount Autofill:** The ANF Extension now supports generating NFS mount code in common languages, currently supports:
  * Python (.py)
  * JavaScript (.js)
  * TypeScript (.ts)
  * C# (.cs)
  * Java (.java)
  * YAML (.yml, .yaml)
