# Email Filter Generator for International Students in Sweden

A proof-of-concept tool that generates email filter strings for international students admitted to Swedish universities. Select your university, copy the filter string, and paste it into Gmail, Outlook, or any email client to automatically label and highlight emails from your university, the Swedish Institute, the Migration Agency, and Ladok.

**[Live Demo](https://k-dgit.github.io/swedish-uni-email-filters/)** (update this URL after enabling GitHub Pages)

## What it does

International students admitted to Swedish universities receive emails from many different addresses throughout the admission process: their department, the housing office, Ladok (tuition system), the Swedish Institute (scholarships), and the Migration Agency (residence permit). Important deadlines can be missed when these emails are scattered across an inbox.

This tool generates a single filter string that catches all emails from a student's university domain, plus key Swedish agencies. The student pastes this string into their email client's filter/rules system, and every relevant email is automatically labelled and starred.

## Features

- **40 Swedish universities and hogskolor** with verified domains and official contact emails
- **Multi-platform setup guide** with step-by-step instructions for Gmail, Outlook, and other email clients
- **Email security awareness section** covering phishing, fake housing scams, fake scholarship emails, and domain verification
- **Single HTML file** with no dependencies, no server, no data collection, no cookies, no external scripts

## Data source

All university domains and contact emails are sourced from [universityadmissions.se](https://www.universityadmissions.se/en/find-out-more/swedish-universities/), the official Swedish admissions portal managed by the Swedish Council for Higher Education (UHR). The data on that page was last updated 14 October 2025.

## Security

This tool was built with a cybersecurity perspective:

- **No user input fields.** The tool outputs hardcoded, verified data only. There is no text input that accepts email addresses, eliminating the risk of users whitelisting malicious addresses.
- **No network calls.** The tool makes zero HTTP requests. No data leaves the page.
- **No external scripts.** All JavaScript is inline and inspectable.
- **No storage.** No cookies, localStorage, sessionStorage, or IndexedDB.
- **No forms.** No form elements, no action attributes, no POST requests.
- **Clipboard API only.** The only browser API used is `navigator.clipboard.writeText()` for the copy button, which writes only data already visible on screen.
- **No eval or dynamic code execution.** All functions are statically defined.
- **innerHTML usage is safe.** The three instances of innerHTML are fed exclusively from hardcoded arrays, not user input.

### Threat model considered

The tool teaches students to create trusted email filters. This is inherently a trust-training behaviour. The design deliberately avoids creating an attack surface by:

1. Not accepting user-supplied email addresses (eliminates lookalike domain risk)
2. Teaching email verification skills in the "Staying Safe" tab (reduces phishing susceptibility)
3. Including a clear disclaimer about independent verification

## How to use

1. Open `swedish-uni-email-filters.html` in any browser
2. Select your university from the dropdown
3. Copy the generated filter string
4. Follow the Setup Guide tab for your email platform (Gmail, Outlook, or other)

## File structure

```
swedish-uni-email-filters.html    # The complete tool (single file)
README.md                         # This file
LICENSE                           # MIT License
```

## Deployment

This is a single static HTML file. To host it:

**GitHub Pages (recommended):**
1. Push this repo to GitHub
2. Go to Settings > Pages
3. Set source to "Deploy from a branch", select `main`, root `/`
4. Your tool will be live at `https://yourusername.github.io/repo-name/`

No build step, no dependencies, no server required.

## Proof of concept

This tool is a proof of concept. It demonstrates how verified university contact data could be used to help international students manage their email during the admission process.

With access to UHR's complete database, this concept could be extended with accurate department-specific emails, integrated into the pre-departure information flow on universityadmissions.se, or adapted for other communication platforms.

## Disclaimer

This tool generates email filter strings using publicly available data from universityadmissions.se. It does not verify, endorse, or guarantee the safety of any email communication. Always verify senders independently before acting on requests involving personal information or payments. This tool is not affiliated with, endorsed by, or maintained by UHR, the Swedish Institute, any Swedish university, or the Swedish government.

## Author

**KingDavid Oyedemi**
MSc Information Security (admitted Autumn 2026), Stockholm University (DSV)
Senior L2/L3 Technical Support Engineer | Cybersecurity Practitioner
ISC2 Certified in Cybersecurity

[LinkedIn](https://linkedin.com/in/king-david-tech) | [GitHub Portfolio](https://github.com/K-Dgit)

Related work:
- [Zero Health Penetration Testing Report](https://github.com/K-Dgit/zero-health-pentest-report) - Full engagement against a vulnerable healthcare web application
- [AWS EC2 Ubuntu Server Deployment](https://github.com/K-Dgit/aws-ec2-ubuntu-server)
- [Starlink Omada SDN Deployment](https://github.com/K-Dgit/starlink-omada-sdn-deployment)

## License

MIT License. See [LICENSE](LICENSE) for details.
