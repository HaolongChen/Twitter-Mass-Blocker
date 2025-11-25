# 🛡️ X/Twitter Mass Blocker (China List)

A robust Userscript to bulk-block over 9,000+ Twitter accounts listed in the [X_based_china repository](https://github.com/pluto0x0/X_based_china).

This script is designed to run directly in your browser while you are logged into X.com. It handles API rate limits, synchronizes with your existing block list to avoid redundant work, and supports concurrent processing for efficiency.

## ✨ Features

*   **Smart Synchronization:** Automatically fetches your *existing* block list first. It only attempts to block users you haven't blocked yet.
*   **Anti-Rate Limit System:** Automatically detects "Too Many Requests" (Error 429) and pauses execution for 3 minutes before resuming.
*   **Anti-Logout (v7):** Refreshes security tokens (`ct0`) before every request to prevent Session Invalidated (Error 401) issues.
*   **Adjustable Speed:** Includes a slider to control concurrency (1 to 5 threads).
*   **Progress Saving:** If the script stops or you refresh, it knows who is already blocked based on the initial sync.

## 🚀 Installation

1.  **Install a Userscript Manager:**
    *   [Tampermonkey](https://www.tampermonkey.net/) (Recommended for Chrome/Edge/Firefox)
    *   Violentmonkey or Greasemonkey.
2.  **Create a New Script:**
    *   Click the Tampermonkey icon -> **Create a new script**.
    *   Delete the default code.
    *   Paste the **Version 7** code provided in the previous step.
    *   File -> **Save**.

## 📖 How to Use

1.  Log in to [X.com](https://x.com).
2.  Once the page loads, look for the **Black Panel** in the bottom-left corner.
3.  **Adjust the Speed Slider:**
    *   **2 Threads (Recommended):** Good balance between speed and safety.
    *   **5 Threads:** Faster, but higher risk of hitting Rate Limits.
4.  Click **START**.
5.  **The Process:**
    *   **Phase 1:** The script will sync your current block list (this might take a few seconds).
    *   **Phase 2:** It downloads the target list from GitHub.
    *   **Phase 3:** It calculates the difference and begins blocking the remaining users.

## ⚠️ Important Warnings regarding Rate Limits

Twitter/X has strict limits on how many actions you can perform.

1.  **Burst Limit (Error 429):**
    *   If you block too many people quickly, X will stop you.
    *   **Script Behavior:** The script will turn **RED** and say "Pausing 3 mins...".
    *   **Action:** **Do not reload.** Let the script wait. It will resume automatically.
2.  **Daily Limit:**
    *   You can typically block roughly **500 - 1,000 users per 24 hours**.
    *   If you hit this limit, the script will pause repeatedly.
    *   **Action:** Stop the script and try again tomorrow.

## 🔧 Troubleshooting

| Error | Meaning | Solution |
| :--- | :--- | :--- |
| **401 Unauthorized** | Your login session keys rotated. | Refresh the page. If that fails, log out and log back in. |
| **429 Too Many Requests** | You are going too fast. | Wait. The script handles this automatically. Lower the slider speed. |
| **Network Error** | Connection timeout. | The script will automatically retry that user. |
| **Panel doesn't appear** | Script didn't load. | Refresh the page. Ensure Tampermonkey is enabled. |

## 📜 Disclaimer

This script is for educational and personal use only. Using automation tools on X (Twitter) carries a risk of shadowbanning or account locking if abused.
*   **Use at your own risk.**
*   **Do not set the speed to max** if you want to keep your account safe.

## 📄 License

MIT License. Free to modify and distribute.
