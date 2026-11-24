# Roadmap

Each day's quiz ends with one **Part** below. Finish it, commit with a message
starting `Part N:` (for example `Part 4: seed securities and prices`), and push.
The next morning's run reviews your SQL, gives feedback, and assigns the next part.

Status: `[ ]` not started · `[~]` in progress · `[x]` done

Files: table definitions in `schema/`, sample data in `seed/`, query sets in `queries/`.

## Phase 1 - Design
- [ ] Part 1: ER design - list entities (clients, accounts, securities, prices, trades, dividends), their attributes, and relationships with cardinality in `DESIGN.md`
- [ ] Part 2: Normalize the design to 3NF and note any decision you made; write `schema/01_tables.sql` with data types and primary keys

## Phase 2 - Build (DDL and constraints)
- [ ] Part 3: Foreign keys, `NOT NULL`, `UNIQUE`, `CHECK` (e.g. quantity > 0, side IN ('BUY','SELL')), `DEFAULT` values
- [ ] Part 4: `ALTER TABLE` practice - add a `sector` column to securities and an index on trades(account_id, trade_date)

## Phase 3 - Data (DML)
- [ ] Part 5: Seed data - 10 clients, 15 accounts, 20 securities across 5 sectors
- [ ] Part 6: Seed ~60 trading days of prices and ~150 trades (a script or generated INSERTs is fine)
- [ ] Part 7: `UPDATE` and `DELETE` practice inside a transaction; demonstrate `ROLLBACK` and `COMMIT`

## Phase 4 - Beginner queries (`queries/01_basics.sql`)
- [ ] Part 8: `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, `LIKE`, `IN`, `BETWEEN`, `IS NULL`
- [ ] Part 9: Aggregates - `COUNT`, `SUM`, `AVG`, `MIN`, `MAX` with `GROUP BY` and `HAVING`

## Phase 5 - Intermediate queries (`queries/02_joins.sql`, `queries/03_subqueries.sql`)
- [ ] Part 10: `INNER JOIN` - each trade with client name and security ticker
- [ ] Part 11: `LEFT JOIN` / anti-joins - clients with no trades, securities never traded; self-join example
- [ ] Part 12: Subqueries - in `WHERE`, in `FROM`, correlated (e.g. trades above that security's average size)
- [ ] Part 13: `UNION`, `CASE` expressions, `EXISTS` vs `IN`

## Phase 6 - Advanced (`queries/04_advanced.sql`)
- [ ] Part 14: Views - `v_current_holdings` (net shares per account per security) and `v_portfolio_value`
- [ ] Part 15: CTEs - multi-step analysis (holdings -> latest price -> value by sector); one recursive CTE (calendar of dates)
- [ ] Part 16: Indexes - use `EXPLAIN` on two slow queries, add indexes, compare

## Phase 7 - Window functions (`queries/05_window.sql`)
- [ ] Part 17: `ROW_NUMBER`, `RANK`, `DENSE_RANK` - top 3 securities by return within each sector
- [ ] Part 18: `LAG` / `LEAD` - daily % price change; biggest single-day moves
- [ ] Part 19: Running totals and moving averages - cumulative cash flow per account, 5-day moving average price
- [ ] Part 20: Capstone report - one query per business question in `queries/06_reports.sql`, and a README section showing results
