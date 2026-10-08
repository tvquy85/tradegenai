# TradeGenAI website

Static marketing site for [tradegenai.com](https://tradegenai.com), hosted on GitHub Pages.
Plain HTML/CSS — no build step.

## Files

| File | Purpose |
|---|---|
| `index.html` | Landing page |
| `privacy.html` | Privacy policy |
| `404.html` | Not-found page (served by GitHub Pages) |
| `styles.css` | All styles, light + dark mode |
| `favicon.svg` | Logo / favicon |
| `CNAME` | Custom domain for GitHub Pages |
| `.nojekyll` | Serve files as-is, skip Jekyll |
| `robots.txt`, `sitemap.xml` | Basic SEO |

## Local preview

```sh
python -m http.server 8000
# open http://localhost:8000
```

## Deploy

1. Push to the `main` branch of `tquy85/tquy85.github.io`.
2. Repo **Settings → Pages** → Source: *Deploy from a branch* → `main` / `(root)`.
3. Custom domain: `tradegenai.com` → after DNS resolves, tick **Enforce HTTPS**.

## DNS (GoDaddy)

Remove the old `A @ → 8.218.17.227`, then add:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | tquy85.github.io |

Do **not** change the MX or SPF (`TXT`) records — they serve `founder@tradegenai.com`.

Check:

```powershell
Resolve-DnsName tradegenai.com -Type A    # 185.199.108-111.153
Resolve-DnsName tradegenai.com -Type MX   # still secureserver.net
```

## Claude for Startups application

- Website: `https://tradegenai.com`
- Email: `founder@tradegenai.com` (also use it for the Claude Console account)
- Description:

> TradeGenAI is building a data analytics and decision-support platform for quantitative finance. We unify market, fundamental and alternative data into a point-in-time research store, run reproducible backtests and risk analytics, and use Claude as a reasoning layer that explains signals, summarizes filings and research, proposes testable hypotheses and drafts decision memos for human review. We are early stage and working with a small group of design partners.
