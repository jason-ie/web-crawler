# Web Crawler for Fakebook

## Project Overview

This project involves the development of a web crawler specifically designed to navigate and extract data from Fakebook, a simulated social networking platform. The crawler's main objective is to collect five unique secret flags hidden across various pages of the Fakebook website. This initiative aims to provide practical experience with the HTTP protocol, web page structure (HTML), and client-server communication mechanisms.

## High-Level Approach

The web crawler was designed to authenticate and navigate through a simulated social networking site, Fakebook, to collect five secret flags hidden across its pages. The script employs Python’s standard libraries to manage HTTP requests, parse HTML content, and maintain session states via cookies.

- Initialization: It starts by establishing a secure HTTPS connection using ssl for encrypted communication with the server.
- Authentication: The crawler retrieves a CSRF token and performs a login using provided credentials, handling cookies to maintain the session.
- Concurrent Navigation: Utilizing concurrent.futures and a ThreadPoolExecutor, the script makes concurrent requests to explore multiple pages in parallel, aiming to efficiently discover and extract secret flags.
- HTML Parsing: The html.parser module is used to parse page content, identifying links for further exploration and extracting flags.
- Link and State Management: A set tracks visited URLs to prevent re-crawling, while a queue manages URLs that need to be visited, ensuring the crawler systematically covers the site without duplication.

## Challenges Faced

- Rate Limiting and Server Load: Implementing concurrent requests while ensuring the crawler does not overwhelm the server was a significant challenge. Balancing speed and politeness required fine-tuning the number of parallel workers.
- Dynamic Content and Parsing: The diverse structure of HTML pages and dynamic content presented difficulties in reliably extracting links and secret flags. Crafting robust parsing logic that could handle various HTML formats was essential.
- Session Management: Maintaining a valid session state across multiple concurrent requests, especially after login and during navigation, required careful handling of cookies and CSRF tokens.

## Testing Strategy

- Unit Testing: Individual components of the crawler, such as the request sending mechanism, HTML parsing function, and cookie management, were tested in isolation using Python’s unittest framework. This ensured reliability and correctness of specific functionalities.
- Integration Testing: The entire crawler was tested as a whole against a simulated environment that mimicked the structure of Fakebook. This environment was crafted to include pages with known flags, links, and various HTML structures to ensure comprehensive testing.
- Concurrent Execution Testing: Special attention was given to testing the crawler’s behavior under concurrent execution. This included verifying that the crawler did not exceed the maximum number of allowed parallel requests and that it correctly managed the session state across these requests.
- Error Handling: The crawler was tested against scenarios such as network failures, server errors, and unexpected HTML structures to ensure it could gracefully handle errors and continue operation.

## Conclusion

This project provided me insights into the understanding of web crawlers and also helped me get a better look at the intricacies of HTTP communication. The importance of ethical considerations in automated data collection was something I didn't really have an idea about before this project as well. The challenges faced prompted innovative solutions and allowed me to better comprehend the importance of rigorous testing in software development.
