# http_desync

HTTP request smuggling / desync tester. Throws CL.TE, TE.CL, CL.CL, chunked encoding, and a few other smuggling techniques at a target and checks the responses for desync indicators. Stores results in SQLite, generates an HTML report and a matplotlib visualization.

Supports proxy (including Tor), concurrent requests, and retries with exponential backoff.

## Setup

```
git clone https://github.com/Unrealisedd/http_desync
cd http_desync
pip install -r requirements.txt
```

## Usage

```
python http_desync_exploiter.py <url> [options]
```

Options:
- `-c` -- concurrency (default 10)
- `-t` -- timeout in seconds (default 10)
- `-d` -- debug mode
- `-p` -- proxy, e.g. `socks5://127.0.0.1:9150`
- `-f` -- file with list of URLs
- `--export-json` -- dump results to JSON

Example:
```
python http_desync_exploiter.py https://example.com -c 15 -t 20 -p socks5://127.0.0.1:9150
```

Output goes to console + `vulnerability_report_<host>.html` + `vulnerability_results_<host>.png` + SQLite db.
