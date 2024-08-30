
---

**Note:** This document provides information about the tool and includes a demo video. Please be aware that no files for the tool are attached.

---

# Trikuta XSS Testing Tool

Trikuta is a private tool designed for testing XSS (Cross-Site Scripting) vulnerabilities by injecting payloads into specified URLs and detecting if the payload is reflected in the HTML source.

## Features

- **Payload Injection:** Injects XSS payloads into the specified URL.
- **Logging:** Logs successful XSS payload reflections to a file.

## Requirements

- Python 3.x
- The following Python packages:
  - argparse
  - errno
  - os
  - sys
  - time
  - splinter
  - bs4 (BeautifulSoup)
  - urllib
  - html

## Usage

To run the Trikuta XSS Testing Tool, use the following command:

```bash
python trikuta.py -u "http://example.com/index.php?name=val&comment=" -p payloads.txt
python trikuta.py -ul urls.txt -p payloads.txt
```

### Command-Line Arguments

- `-u`: The URL to inject XSS payloads into. The `{xss}` placeholder should be included in the URL.
- `-ul`, `--url_list`: The file containing a list of URLs to test.
- `-p`: The payload list to use for injection.
- `-t`: (Optional) Amount of time (in seconds) to delay between requests.

### Example

```bash
python trikuta.py -u "http://example.com/index.php?name=val" -p payloads.txt -t 1
python trikuta.py -ul urls.txt -p payloads.txt -t 1 
```

## Output

- If XSS vulnerabilities are detected, they will be printed in the terminal and logged to a file if confirmed by the user.

## Logging

The tool will save the results to a `target_name.txt` file . The results will be saved in the `results` directory.
