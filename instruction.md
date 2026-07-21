Parse the Apache-style access log at `/app/access.log` and write a JSON summary
report to `/app/report.json`.

The report must be a JSON object with exactly these keys:

- `total_requests` (integer): number of non-empty lines in `/app/access.log`
- `unique_ips` (integer): number of distinct client IP addresses (first field of each line)
- `top_path` (string): the request path that appears most often in the quoted request
  (the path after the HTTP method, e.g. `/index.html`)

Success criteria:

1. `/app/report.json` exists.
2. `/app/report.json` is valid JSON and contains the keys `total_requests`,
   `unique_ips`, and `top_path`.
3. `total_requests` equals the number of non-empty lines in `/app/access.log`.
4. `unique_ips` equals the number of distinct client IPs in `/app/access.log`.
5. `top_path` equals the most frequent request path in `/app/access.log`.
