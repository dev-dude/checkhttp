# CheckHTTP MCP Server Configuration

This repository provides the configuration to connect your AI coding assistant (Cursor, VS Code, Claude Desktop) to [CheckHTTP](https://checkhttp.com), allowing your AI agent to instantly deploy uptime monitoring and SSL checks

## 🚀 Quick Start

### 1. Clone or Download
Clone this repository into the root of your project workspace.

### 2. Configure Your Editor

#### For Cursor
1. Go to **Cursor Settings** > **Tools & MCP** 
2. Enable on the checkbox
5. (Optional) Add your API Key in Headers if you have a paid plan, otherwise the free tier is used automatically.

#### For VS Code (using MCP Extension)
1. The included `.vscode/mcp.json` file should be automatically detected.
2. Click Start on the mcp.json 


## 🤖 Usage

Once connected, you can ask your AI agent to perform monitoring tasks.

### Example Prompts

**Deploy Monitoring:**
> "setup_monitoring https://api.mysite.com admin@mysite.com"

**Check Status: (Make sure API Key is Configured sent to your email)**
> "check_status https://api.mysite.com"

## 🛠 Available Tools

The MCP server exposes the following tools to your agent. Note that some tools require authentication via an API Key (sent to your email after setup).

### Public Tools

- **`setup_monitoring`**
  - *Description:* Initialize monitoring. Creates an account and sends an API Key to your email.
  - *Arguments:*
    - `url` (string, required): The website URL to monitor.
    - `email` (string, required): Your email address.

### Authenticated Tools (Requires API Key)

- **`list_monitors`**
  - *Description:* List all monitors configured for your account.
  - *Arguments:* None

- **`check_status`**
  - *Description:* Check the status of your monitored sites.
  - *Arguments:*
    - `siteUrl` (string, optional): Filter by site URL.

- **`disable_monitor`**
  - *Description:* Disable (pause) a monitored site.
  - *Arguments:*
    - `siteId` (integer, required): The ID of the site to disable.

- **`resume_monitor`**
  - *Description:* Resume a disabled monitored site.
  - *Arguments:*
    - `siteId` (integer, required): The ID of the site to resume.

- **`delete_monitor`**
  - *Description:* Delete a monitored site.
  - *Arguments:*
    - `siteId` (integer, required): The ID of the site to delete.
    - `confirm` (boolean, required): Set to true to confirm deletion.

- **`verify_ssl_certificate`**
  - *Description:* Check the SSL certificate details and validity for a URL.
  - *Arguments:*
    - `url` (string, required): The URL to check (must be HTTPS).

---

*Powered by [CheckHTTP](https://checkhttp.com) - Reliable uptime checks for AI Agents.*
 
