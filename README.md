# Prexel Markets Pro for Cursor

Read live Bitcoin Synthesis, the saved Daily Brief, and signal or domain evidence pinned to one capture. Research is read-only; observations are not trading recommendations. Live access does not make every source current: retain each source clock, freshness and gap. The Daily Brief is a saved edition with its own cutoff and generation time.

Connect an existing Prexel account with Pro access through Cursor's OAuth sign-in. The server uses the `markets:read` scope. This package contains no credentials and does not create an account, grant access, execute trades, change billing or initiate checkout.

## Workflows

- `/pro-morning-read` builds a concise market read with a counterpoint and material gaps.
- `/pro-thesis-check` checks a specific thesis against supporting and conflicting captured observations.

After installing and enabling this plugin, invoke a workflow or ask Cursor to use it. Start with the Synthesis overview, then inspect only the evidence needed for the requested claims. The workflows require exact comparators, thresholds, units and windows; missing evidence cannot explain why a signal disappeared.

Try: “Use pro-morning-read for a concise Bitcoin read: the main observation, one counterpoint and material gaps.”

For a thesis check: “Use pro-thesis-check: do Bitcoin positioning and ETF flows support the same bullish reading? Show evidence on both sides and keep their clocks visible.”

## Tools

| Tool | Supported workflow |
| --- | --- |
| `get_synthesis` | Read a BTC capture; pin `cycle_id` and use `offset` / `limit` for returned signal pages. |
| `get_daily_brief` | Read a saved edition; pin `report_id` and expand returned `path` / `offset` pages. |
| `get_signal_evidence` | Inspect one returned `signal_id` at the same `cycle_id`; expand returned `path` / `offset` pages. |
| `get_domain_evidence` | Inspect a named domain at the same `cycle_id`; expand returned `path` / `offset` pages. |

Domains are `on_chain`, `positioning`, `technicals`, `macro`, `sentiment`, `prediction_markets` and `etf_flows`. The tools serve BTC only. A signal example or selected relationship input is not a complete criteria audit. Preserve partial and unavailable evidence; an expired capture must not be silently replaced.

## Direct MCP connection

[Add Prexel Markets Pro to Cursor](https://cursor.com/link/mcp/install?name=prexel-markets-pro&config=eyJ1cmwiOiJodHRwczovL21hcmtldHMucHJleGVsLnh5ei9tY3AvcHJvIn0=). Confirm the connection and complete Prexel OAuth sign-in with an account that already has Pro access. This installs the MCP connection only, not the bundled workflows.

Or merge this entry into Cursor's MCP settings without replacing existing servers:

```json
{
  "mcpServers": {
    "prexel-markets-pro": {
      "url": "https://markets.prexel.xyz/mcp/pro"
    }
  }
}
```

If authentication or entitlement is unavailable, the research cannot be read. Complete the host's sign-in flow or contact support; do not paste tokens into a prompt or configuration. No static client secret is required by this package.

Use returned source URLs only for claims they support. A Synthesis link is a rolling view that may show a different capture. A Daily Brief link, when returned as an exact edition, identifies that saved report. Capture generation, source observation and Brief cutoff clocks remain distinct.

[Connection guide](https://prexel.xyz/mcp/) · [Privacy](https://prexel.xyz/privacy/) · [Terms](https://prexel.xyz/terms/) · [Support](https://prexel.xyz/support/) · mcp@prexel.xyz

## Licence and branding

The wrapper configuration, this guide and the workflow skills are available under [the MIT licence](LICENSE), adapted from the Prexel Markets Free public wrapper. This grant does not include the hosted Prexel service, private Nexus source, research payloads or third-party market data. Access to the service remains subject to [Prexel's terms](https://prexel.xyz/terms/).

Prexel branding, including `assets/logo.png`, is excluded from the MIT grant. No rights are granted to imply Prexel affiliation or endorsement of a derivative. Separate distribution and brand-use permissions granted to marketplace platforms under their publisher terms remain unaffected.
