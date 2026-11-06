# Aisle Bot

Ask Claude about the grocery history you keep in the Aisle Intelligence iPhone app, by typing or by voice. Claude answers from your own trips, the items on them, the prices you paid, and your grocery list.

## What you need

- The Aisle Intelligence iPhone app and an active Plus subscription.
- A code from the app. In the app, go to Stores & data, then Connect to Claude or ChatGPT, and tap Connect. Type the code on the sign-in page at api.aisleintelligence.app.

## What you can ask

- How much did I spend on groceries last month?
- What did I pay for eggs at each store?
- What did I buy on my last trip?
- What's on my grocery list?

## What's in this plugin

The plugin holds no program code. It has two parts:

- **A connector** to `https://api.aisleintelligence.app/mcp`, run by RVAi Consulting LLC. You sign in to it with OAuth and the code from the app.
- **A skill** that tells Claude which tool to use and how to report the results.

## What it reads and sends

The connector has four read-only tools:

| Tool | What it returns |
|---|---|
| `list_trips` | Date, store, total, and item count for your trips from the last 13 months. |
| `list_items` | Name, category, date, store, and price, when the receipt showed one. |
| `get_my_prices` | The latest, lowest, and highest price you paid for an item at each store. |
| `get_grocery_list` | Each line's text and quantity, and whether it's checked off. |

Each time Claude uses a tool, the plugin sends that tool's arguments, such as a date range or an item name, to `api.aisleintelligence.app`. The results go to Claude. The plugin sends data to no other service.

**What it can't do:** it can't change anything, add to your list, or buy anything. It can't read your receipt photos, passwords, loyalty numbers, or name. It leaves out pharmacy and health items it recognizes, so a trip's total can be more than its listed items. It shows your own prices only, not other shoppers' prices or shelf prices.

**Your data:** when you tap Connect, the app sends our server an encrypted copy of this data and keeps it current. Tap Disconnect in the app, or use Delete all data, and we delete our copy and end Claude's access. Access also ends when Plus ends, and we delete our copy 7 days after that. What Claude already read stays in your chats until you delete those chats. Read our [privacy policy](https://aisleintelligence.app/legal/plus/#privacy-policy).

## Support

Go to [aisleintelligence.app/support](https://aisleintelligence.app/support/), or email partnerships@aisleintelligence.app.

Aisle Bot is made by RVAi Consulting LLC. It isn't made or endorsed by Anthropic.
