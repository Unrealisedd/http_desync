# HTTP Desynchronization Vulnerability Exploiter

## Description

This tool is designed to identify and exploit HTTP desynchronization vulnerabilities. It probes web servers for misconfigurations or behaviors that could allow an attacker to perform attacks such as request smuggling. The tool supports various HTTP request smuggling techniques and provides detailed analysis and visualization of the results.

## Features

- Automated detection of server-side discrepancies in processing HTTP requests
- Support for various HTTP request smuggling techniques (e.g., CL.TE, TE.CL, CL.CL)
- Visualization of server response behaviors to highlight possible vulnerabilities
- Detailed HTML report generation
- SQLite database integration for result storage
- Proxy support, including Tor integration
- Concurrent request handling for efficient testing
- Customizable payload generation
- Advanced response analysis, including timing and status code checks

## Installation

1. Clone this repository:
 ```
git clone https://github.com/Unrealisedd/http_desync
 ```
2. Install the required dependencies:
```
pip install -r requirements.txt
```

## Usage

Run the tool from the command line with the following syntax:
```
python http_desync_exploiter.py [URL] [OPTIONS]
```

### Options:

- `-c, --concurrency`: Number of concurrent requests (default: 10)
- `-t, --timeout`: Request timeout in seconds (default: 10)
- `-d, --debug`: Enable debug mode
- `-p, --proxy`: Proxy URL (e.g., socks5://127.0.0.1:9150 for Tor)

### Example:
```
python http_desync_exploiter.py https://example.com -c 15 -t 20 -d -p socks5://127.0.0.1:9150
```

This command will test `https://example.com` with a concurrency of 15, a timeout of 20 seconds, in debug mode, and using a Tor proxy.

## Output

The tool provides the following outputs:

1. Console output with detailed results
2. Visualization of results saved as `vulnerability_results.png`
3. HTML report generated as `vulnerability_report.html`
4. SQLite database `vulnerability_results.db` containing all test results

## Caution

This tool is for educational and authorized testing purposes only. Misuse of this tool may be illegal and unethical. Always obtain proper authorization before testing any systems you do not own or have explicit permission to test.

## Contributing

Contributions to improve the tool are welcome. Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes and commit (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

The author of this tool is not responsible for any misuse or damage caused by this program. Use at your own risk.
