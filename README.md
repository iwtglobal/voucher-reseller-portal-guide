# Voucher Reseller Portal Guide

An educational guide to the **reseller portal** in **gift card voucher distribution**: how distributors, sub-dealers, and retailers in a reseller hierarchy buy stock, manage their downline, and sell electronic vouchers. Written for telecom operators, gift card programs, and distributors evaluating platforms in the [EVD System](https://evdsystem.com/) and [MoboGage](https://evdsystem.com/about-mobogage/) family.

---

## What Is a Voucher Reseller Portal?

A **voucher reseller portal** is the self-service web or app interface that each member of a distribution chain uses to run their part of the business. A master distributor uses it to fund their account, set prices and commissions for sub-dealers, and watch sales across their network. A retailer uses it to top up their balance, sell airtime PINs or gift card codes, and download statements.

Without a portal, every balance transfer, price change, and statement request goes through the operator's back office by phone or spreadsheet. With a good portal, the operator sets the rules once and the hierarchy runs itself, which is what lets an electronic voucher distribution network scale to thousands of points of sale.

### Who uses it

- **Master distributors** — buy bulk stock or float, manage regional dealers  
- **Sub-dealers / wholesalers** — serve a territory of retailers  
- **Retailers and agents** — sell to end customers at the counter, POS, or app  
- **Corporate buyers** — order bulk gift cards for employees or customers  

---

## Architecture Overview: Hierarchy-Aware Self-Service

```
Operator / brand (catalog, base prices, rules)
        │
        ▼
Master distributor portal (pricing, downline, float)
        │
        ▼
Sub-dealer portal (territory, retailer onboarding)
        │
        ▼
Retailer portal / POS app (sell, top up, statements)
        │
        ▼
Shared ledger + inventory + audit trail
```

### Core portal modules

| Module | What it does |
|--------|--------------|
| **Account and float** | Shows balance, credit limit, and funding history |
| **Stock transfer** | Moves balance or voucher stock down the hierarchy |
| **Downline management** | Onboard, suspend, and set limits for child accounts |
| **Pricing and commission** | Set margins within limits the parent allows |
| **Sales and ordering** | Sell single vouchers or order bulk batches |
| **Reports and statements** | Sales by product, period, and child account |
| **Users and roles** | Staff logins with permissions and two-factor authentication |

See [docs/glossary.md](./docs/glossary.md) for terminology.

---

## How the Reseller Portal Works, Step by Step

### 1. The operator defines the catalog and rules

Products, denominations, base prices, and the maximum margin each hierarchy level may add are set centrally.

### 2. Each level funds its account

Resellers prepay or draw on an approved credit line. The portal shows available balance in real time.

### 3. Parents manage children

A distributor creates sub-dealer accounts, assigns territories, sets their commission within the allowed range, and transfers float to them.

### 4. Retailers sell

Retailers sell vouchers through the portal, a POS terminal, or an app. Each sale debits their balance and is credited to the commission ledger of every level above them.

### 5. Everyone reconciles from the same data

Statements at each level come from the same ledger, so a distributor's report of retailer sales matches the retailer's own statement.

---

## Design Principles

1. **Visibility follows hierarchy** — a reseller sees their own account and their downline, never siblings or parents' margins.  
2. **Rules are inherited** — a child cannot sell below cost or exceed a margin cap set above them.  
3. **Every transfer is a ledger posting** — no balance edits without a matching entry.  
4. **Self-service with guardrails** — limits, approvals, and two-factor authentication on sensitive actions.  
5. **Mobile-first for retailers** — most small shops run on a phone or POS, not a desktop.

Platforms such as EVD System / MoboGage provide multi-tier reseller management with portals, Android and Linux POS, apps, and APIs for telecom airtime, gift cards, and loyalty vouchers.

---

## Implementation Considerations

- **Role-based access** — owner, cashier, and accountant roles per reseller account  
- **Credit limits and collection** — clear rules for postpaid resellers  
- **Bulk operations** — CSV upload for onboarding or stock transfers in large networks  
- **Localization** — language, currency, and tax formats per market  
- **Session security** — two-factor login, device binding, and idle timeouts  
- **API parity** — larger resellers integrate their own systems through the same rules  

---

## FAQ

**What is a voucher reseller portal?**  
A self-service interface where distributors, sub-dealers, and retailers manage balances, downline accounts, pricing, sales, and statements in an electronic voucher or gift card distribution network.

**How does a reseller hierarchy work in gift card voucher distribution?**  
Value and stock flow from the operator to master distributors, then to sub-dealers and retailers. Each level earns a margin or commission on sales made by its own account and its downline.

**Can a reseller set their own prices?**  
Usually within limits. The operator or parent sets a floor and a maximum margin, and the portal enforces them.

**How do resellers top up their balance?**  
By bank transfer, mobile money, cash deposit with a parent, or an approved credit line, depending on how the operator configures funding.

**How does this relate to MoboGage / EVD System?**  
EVD System is MoboGage's electronic voucher distribution platform. See the [multi-tier reseller voucher distribution](https://evdsystem.com/evd-software/multi-tier-reseller-voucher-distribution/) article and the [EVD System home](https://evdsystem.com/) when evaluating product fit.

---

## Further Reading / Related Industry Resources

- [Multi-tier reseller voucher distribution](https://evdsystem.com/evd-software/multi-tier-reseller-voucher-distribution/) — how reseller hierarchies work in EVD  
- [EVD System home](https://evdsystem.com/) — platform overview for digital value distribution  

---

## License

Documentation in this repository is provided under the MIT License. See [LICENSE](./LICENSE).

*Educational material only. Not a substitute for vendor due diligence. MoboGage and EVD System refer to offerings on evdsystem.com.*
