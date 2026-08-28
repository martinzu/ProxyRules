# ProxyRules

Personal routing rules for Shadowrocket.

## AI rules

Use the following URL as a `RULE-SET`:

```text
https://raw.githubusercontent.com/martinzu/ProxyRules/main/Rule/AI.txt
```

The rules cover OpenAI, Apple Intelligence, Claude, Microsoft Copilot,
GitHub Copilot, Google Gemini, Google AI Studio, NotebookLM, Grok,
OpenRouter, and Perplexity.

Gemini desktop app endpoints are kept as exact domain matches where possible
to avoid routing all Google and YouTube traffic through the AI policy.

## NekoBox / NekoRay

`NekoBox/AI-domains.txt` uses the domain syntax accepted by the routing editors
in NekoRay for Windows and NekoBox for Android:

- `full:` for an exact domain
- `domain:` for a domain suffix
- `keyword:` for a domain keyword

On Android, create a routing rule, paste the file contents into its domain
field, and select the AZ profile as its outbound. Keep the HK profile as the
default profile. Subscription imports only import outbounds and do not import
these routing rules.

On the archived Windows NekoRay client, paste the same list into **Routing
Settings > Proxy Domain**. That field routes to the currently active proxy, so
the old GUI cannot reliably select AZ for this list while keeping HK as the
default. For two-proxy routing, use a sing-box custom configuration with both
outbounds, or migrate to a maintained sing-box GUI.

`sing-box/AI.json` is a standard sing-box source-format headless rule set for
clients that support remote sing-box rule sets.

`sing-box/route-example.json` shows the corresponding remote rule-set route.
Its `az` and `hk` values are outbound tags and must match the tags in the full
sing-box configuration; it is a fragment, not a complete standalone profile.
