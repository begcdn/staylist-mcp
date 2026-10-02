# Staylist World (staylist.world): free hotel comparison for AI assistants

Staylist World is a free hotel comparison service for people and their AI assistants. It compares 77,000+ hotels on the same criteria: an AI score built from guest ratings and reviews, amenities, distance to transit and previously observed prices. It shows where each fact comes from and marks unknowns as unknown. No hotel can pay to rank higher.

Add one URL to your assistant and it can shortlist hotels for a trip, compare them and explain its pick. No account, no API key.

```
https://staylist.world/mcp
```

Remote MCP server · Streamable HTTP · no authentication · free. For a personal link (your own rate-limit allowance), open [staylist.world/connect](https://staylist.world/connect).

## Set it up

| Assistant | How | Plan |
|---|---|---|
| Claude | Settings → Connectors → Add custom connector → paste the URL ([guide](https://staylist.world/connect/claude)) | Free (one custom connector) and paid |
| Claude Code | `claude mcp add --transport http staylist https://staylist.world/mcp` | Free |
| ChatGPT | Settings → Apps & Connectors → Advanced → Developer mode, then add the URL | Plus, Pro, Business |
| Grok | grok.com/connectors → New Connector → Custom | Web, iOS, Android |
| Muse (Meta) | Ask Muse to add a custom connector at the URL ([guide](https://staylist.world/connect/muse)) | US |
| Perplexity | Custom connector | Pro, Max |
| Le Chat (Mistral) | Connectors → add MCP connector | Free and paid |
| Cursor, VS Code, Codex, Gemini CLI | Add a remote HTTP MCP server ([examples](examples/)) | Free |

**No connector?** Any assistant that can read web pages can use a city page directly:

> Read https://staylist.world/hotels-in/rome and recommend a quiet hotel near Spagna metro under $250 a night. Explain why.

Each hotel row lists its score, star class, typical price, area, nearest station with distance, key amenities and who it suits.

## Tools

| Tool | What it returns |
|---|---|
| `search_hotels` | Up to 20 hotels for a city, name or preference ("pool", "breakfast"), compared on the same fields: score and its source, star class, area, nearest station, amenities, typical price |
| `get_hotel` | Staylist's AI overview (pros, cons, who it suits), how the hotel compares with others in its city, check-in/out times, child policy, nearest airport and station |
| `get_booking_link` | The booking page for the chosen hotel, plus its Staylist page |
| `list_destinations` | Popular starting points (any city can be searched) |

Empty fields mean unknown, not bad. Prices are previously observed; the booking site shows the live price and availability for your dates. Staylist does not book or take payment.

## Example prompts

- "3 nights in Rome near the Spanish Steps, quiet room, under $250. Compare the best options and pick one."
- "Bangkok with kids: a hotel with a pool near the BTS, around $150 a night."
- "Las Vegas weekend: the best-rated hotel with a spa, and why."
- "Is Hotel Damaso in Rome good? What do guests complain about?"

## Also available

- REST API with an OpenAPI spec: [staylist.world/api-docs](https://staylist.world/api-docs) · [openapi.json](https://staylist.world/api/openapi.json)
- Agent guide: [staylist.world/agents](https://staylist.world/agents) · [llms.txt](https://staylist.world/llms.txt)
- Markdown version of any city or hotel page: request it with `Accept: text/markdown`
- Listed in the official MCP Registry as `world.staylist/staylist`, and on [Smithery](https://smithery.ai/servers/ghaladoghalado/staylist) and [Glama](https://glama.ai/mcp/connectors/world.staylist/staylistworld)

## Limits

Fair use: 60 requests a minute per person with a personal link. Send only travel search terms, never personal or payment details. Coverage is strongest in large tourist cities; AI overviews cover a growing share of hotels.

## Contact

support@staylist.world · [staylist.world](https://staylist.world) · [How Staylist compares hotels](https://staylist.world/about)
