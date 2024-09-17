# Hunter - Email Scraper & Verifier

![Hunter Logo](logo.png) 

**Hunter** is a Python tool for educational purposes that helps in vulnerability reporting. It quickly finds and verifies email addresses associated with a domain, assisting in contacting the right parties. It must not be used for social engineering or any malicious activities. The developer is not liable for misuse.

### Features:
- **Email Discovery**: Automatically retrieve email addresses linked to any domain.
- **Email Verification**: Validate each email based on its score:
  - **Risky** (Score < 60)
  - **Valid and Active** (Score < 100)
  - **Valid and Highly Active** (Score ≥ 100)
- **Color-Coded Output**: Easily identify the email status with clear visual cues.


### Why Use Hunter?
If you’ve found a vulnerability and need to get in touch with the responsible parties, **Hunter** streamlines the process by fetching the associated email addresses for you. It verifies these addresses so you can reach out to the most reliable contacts.

### Installation:
1. **Clone the repo**:
   ```bash
   git clone https://github.com/0xgh057r3c0n/Hunter.git
   cd Hunter
   ```
2. **Install dependencies**:
   ```bash
   pip install requests termcolor
   ```

### Usage:
1. **Set your Hunter.io API key** in the script (`API_KEY` variable).
2. **Run the script**:
   ```bash
   python3 hunter.py
   ```
3. **Enter the domain** when prompted, and the tool will fetch and verify the associated emails.

### Example

```bash
[*] Enter the domain to check for emails (e.g., example.com): example.com
[*] Fetching emails for domain: example.com...
[*] Verifying 'email@example.com'
[*] email@example.com is valid and active
```

### Requirements:
- Python 3.x
- `requests`, `termcolor`

### License:
MIT License - see [LICENSE](LICENSE) for details.

### Contributing:
Contributions are welcome! Feel free to submit issues or pull requests to improve the tool.
