# CresMarr Company Handbook

**CresMart | Africa's Gateway to Global Trade**
Data and analytics team, an initiative of Maths & Data.

This handbook explains how our team works. Everything here applies to both team members. If something changes, we change it here through a pull request.

---

## 1. Team and roles

| Role | Name | Team | Main repo |
| --- | --- | --- | --- |
| Head of Data / Data Scientist | Edwin Sunday UMANA | data-science-engineering | `delivery-delay-ml` |
| Data Analyst | Precious Mojalaoluwa OJO | analytics | `logistics-analytics` |

Shared repos: `data-platform` (database schema, data dictionary, loading scripts) and this handbook.

## 2. The project

**CresMart Delivery Performance and Delay Prediction.** We simulate a logistics business using the public Olist Brazilian E-Commerce dataset (about 100,000 orders, 2016 to 2018).

- The analytics team measures delivery performance and explains where and why deliveries are late.
- The data science team predicts which orders will be late.
- Insights flow one way and predictions flow back: her findings guide the model's features, and the model's predictions feed her dashboards.

Dataset: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

---

## 3. Phase 1 notice: Data Foundations (Weeks 1 to 4)

**Start date:** 15-10-2026  **Phase review:** [5-11-2026, end of Week 4]

### Objective
By the end of Phase 1 we have the data loaded, documented and understood, the key delivery metrics agreed and measured, a first dashboard, and a clear list of what might cause late deliveries.

### Task allocation

| Week | Task | Owner | Deliverable |
| --- | --- | --- | --- |
| 1 | Set up tools and download the dataset | Both | Working setup, data in `data/raw/` locally |
| 1 | Document all tables in a data dictionary | Both (split) | `data-platform/data-dictionary/` |
| 1 to 2 | Build the PostgreSQL database and loading scripts | Data Scientist | `data-platform/schema/` and `etl/` |
| 1 to 2 | Clean and join orders data, create delivery fields | Data Analyst | Cleaned dataset and steps in `logistics-analytics/excel/` |
| 2 | Agree KPI definitions | Both | Section 5 of this handbook |
| 2 to 3 | Exploratory analysis and target definition | Data Scientist | Notebook in `delivery-delay-ml/notebooks/` |
| 3 | KPI queries and pivot analysis | Data Analyst | `logistics-analytics/sql/` and `reports/` |
| 3 to 4 | Power BI dashboard v1 | Data Analyst | `logistics-analytics/powerbi/` |
| 4 | Phase 1 report and hypotheses on late-delivery drivers | Data Analyst | `logistics-analytics/reports/` |
| 4 | Feature list v0 and data quality report | Data Scientist | `delivery-delay-ml/docs/` |

Detailed instructions for each person are in the README of their own repo.

### Phase 1 exit criteria
- [ ] Data dictionary complete for all tables
- [ ] Database loads from scripts on a clean machine
- [ ] KPI definitions agreed and written below
- [ ] Dashboard v1 reviewed in a Friday demo
- [ ] Analyst's hypotheses handed to the data science team
- [ ] Every Phase 1 task closed through a pull request

---

## 4. How we work

**Weekly rhythm** (all times in [agreed time zone])

| Day | Meeting | Length |
| --- | --- | --- |
| Monday | Sprint planning | 30 min |
| Sunday | Standup, Demo and retro | 60 min |

- **Daily update:** one short written post each working day in GitHub Discussions (done, next, blockers).
- **Weekly report:** a short written report each Friday, saved in the private `company-admin` repo.
- **Hours:** about [10 to 15] hours per week each.
- **Replies:** answer messages within 24 hours. Say early if you are blocked or a deadline will slip.

**Code and file rules**
1. Every task starts as an issue on the project board.
2. Work happens on a branch, never directly on `main`.
3. Every change goes through a pull request reviewed by the other person.
4. Use clear commit messages, for example `Add delivery_days calculation`.
5. Never commit raw data, passwords, tokens or personal information.

**Definition of Done:** the work meets the issue's description, is documented, has been reviewed and merged, and the issue is closed.

---

## 5. KPI definitions (to be agreed in Week 2)

| KPI | Definition |
| --- | --- |
| Delivery days | Customer delivery date minus purchase date |
| Delay days | Customer delivery date minus estimated delivery date |
| Late flag | 1 if delivered after the estimated date, otherwise 0 |
| On-time delivery rate | Share of delivered orders that are not late |
| Late rate by segment | Late flag average by state, seller and product category |
| Freight share | Freight cost as a share of order value |

## 6. Data handling
- Repos are private for now. Nothing leaves the team without both of us agreeing.
