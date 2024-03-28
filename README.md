# Web Crawler for Fakebook

## Project Overview

This project involves the development of a web crawler specifically designed to navigate and extract data from Fakebook, a simulated social networking platform. The crawler's main objective is to collect five unique secret flags hidden across various pages of the Fakebook website. This initiative aims to provide practical experience with the HTTP protocol, web page structure (HTML), and client-server communication mechanisms.

## High-Level Approach

The crawler is implemented in Python and operates by sending HTTP/1.1 requests to interact with the web server. Initially, it fetches the CSRF token required for authentication and then logs in using provided credentials. Post-login, it systematically traverses the site, parsing HTML content to find links and secret flags while managing cookies and handling various HTTP response codes efficiently. The approach emphasizes respectful crawling practices, such as limiting request rates and adhering to robots.txt guidelines where applicable.

## Key Features

Secure HTTPS Communication: Implements TLS wrapping over TCP sockets to ensure secure data transmission.
Session Management: Handles cookies to maintain session state across requests.
Dynamic Content Parsing: Uses html.parser from Python's standard library to parse HTML and extract data.
Robust Link Management: Keeps track of visited URLs and prioritizes new links, avoiding infinite loops and redundant visits.
Error Handling: Gracefully manages HTTP redirects and common error codes like 404 (Not Found) and 503 (Service Unavailable).

## Challenges Faced

Session Management Complexity: Ensuring the crawler correctly handles session cookies was particularly challenging, especially in maintaining the session across redirects and re-authentication scenarios.
Dynamic Content Navigation: Parsing HTML to accurately extract links and secret flags, while accounting for relative URLs and dynamically generated content, required careful implementation and testing.
Rate Limiting and Ethics: Balancing the need for thorough site coverage with ethical crawling practices, such as rate limiting and obeying robots.txt, posed an ongoing consideration throughout development.

## Testing Strategy

### Local Testing Environment

Mock Server Setup: Implemented a local HTTP server with predefined HTML pages to simulate the Fakebook environment, enabling controlled testing of the crawler's capabilities without impacting the actual site.
Unit and Integration Tests
Modular Testing: Developed unit tests for individual components, such as link extraction and cookie management, using Python's unittest framework.
Integration Testing: Conducted comprehensive tests to evaluate the crawler's performance in real-world scenarios, including handling redirects and parsing complex HTML structures.

## Debugging and Logging

In order to debug, I utilized logging to track the crawler's decisions and network activity, which helped in the identification and resolution of issues encountered during development.

## Conclusion

This project provided me insights into the understanding of web crawlers and also helped me get a better look at the intricacies of HTTP communication. The importance of ethical considerations in automated data collection was something I didn't really have an idea about before this project as well. The challenges faced prompted innovative solutions and allowed me to better comprehend the importance of rigorous testing in software development.
