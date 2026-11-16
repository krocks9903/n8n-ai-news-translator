# n8n AI News Translator

An automated workflow built with n8n that fetches the latest news from an RSS feed, translates articles to Hindi using Google Translate, and delivers formatted daily email summaries.

> **Current feed:** the exported workflow (`Auto email.json`) reads NASA's news release feed (`https://www.nasa.gov/news-release/feed/`). It was first built against Wired's AI feed (`https://www.wired.com/feed/tag/ai/latest/rss`). To switch, change the URL in the **RSS Read** node. The email template still says "AI Intelligence Brief" in the header and "Wired AI Feed" in the footer, whichever feed is set.

## Overview

This project demonstrates the power of n8n's visual workflow automation by creating a completely hands-off news aggregation and translation service. Perfect for staying updated with AI developments in your preferred language.

## Features

- **RSS Feed Integration**: Pulls the latest items from the feed set in the RSS Read node
- **Content Limiting**: Processes top 6 most recent articles to keep emails manageable
- **Dual Translation**: Translates both headlines and article content to Hindi
- **Email Automation**: Sends beautifully formatted HTML emails via Gmail
- **Visual Workflow**: Built entirely with n8n's drag-and-drop interface

## Workflow Steps

1. **Manual Trigger**: Starts the workflow execution
2. **RSS Read**: Fetches the latest items from the configured feed (NASA news releases in the current export)
3. **Content Limiter**: Restricts to 6 most recent articles
4. **Parallel Translation**: Simultaneously translates titles and content
5. **Data Merging**: Combines translated content with original data
6. **Field Mapping**: Structures data for email formatting
7. **Content Aggregation**: Prepares all articles for single email
8. **Email Delivery**: Sends formatted summary via Gmail

## Prerequisites

- n8n instance (cloud or self-hosted)
- Google Translate API credentials
- Gmail OAuth2 setup
- Basic understanding of n8n workflows

## Setup Instructions

1. **Import Workflow**
   ```bash
   # Import the Auto email.json file into your n8n instance
   ```

2. **Configure Credentials**
   - Set up Google Translate OAuth2 API access
   - Configure Gmail OAuth2 credentials
   - Update recipient email address in the Gmail node

3. **Test Workflow**
   - Execute manually to verify all connections work
   - Check email delivery and formatting

4. **Schedule (Optional)**
   - Replace manual trigger with Cron trigger for daily automation
   - Set preferred delivery time

## Configuration

### Email Settings
- **Recipient**: Update in the Gmail node parameters
- **Subject**: "Daily News Summary" (customizable)
- **Format**: HTML with styled article blocks

### Translation Settings
- **Source Language**: Auto-detected from English content
- **Target Language**: Hindi (`hi`) - easily changeable
- **API**: Google Translate (requires valid credentials)

### Content Filtering
- **Source**: NASA news release feed in the current export (set in the RSS Read node)
- **Article Limit**: 6 articles (adjustable in Limit node)
- **Content**: Full article text and headlines

## File Structure

```
n8n-ai-news-translator/
├── Auto email.json                    # n8n workflow export
├── README.md                          # This file
├── Screenshot 2025-09-14 170615.png   # Workflow canvas in n8n
├── Screenshot 2025-09-14 170629.png   # Sample output text in Hindi
└── Screenshot 2025-09-14 170640.png   # The same text in English
```

## Customization Ideas

- **Multiple Languages**: Add parallel translation nodes for different languages
- **Multiple Sources**: Include additional RSS feeds (TechCrunch, VentureBeat, etc.)
- **Content Filtering**: Add keyword filtering or sentiment analysis
- **Delivery Options**: Send to Slack, Discord, or other platforms
- **Scheduling**: Set up automated daily/weekly delivery

## Dependencies

- n8n (v0.196.0+)
- Google Translate API
- Gmail API
- Active internet connection for RSS feeds

## Why n8n?

This project showcases n8n's strengths:
- **Visual Development**: No coding required for complex workflows
- **Pre-built Integrations**: Extensive node library for common services
- **Data Flow Management**: Intuitive handling of data transformations
- **Scalability**: Easy to extend and modify workflows

## Contributing

Feel free to fork this project and adapt it for your needs. Some enhancement ideas:
- Add error handling and retry logic
- Implement content deduplication
- Create multi-language support
- Add article summarization using AI

## License

This project is open source and available under the MIT License.

## Acknowledgments

- n8n team for building an amazing automation platform
- Wired for providing quality AI news content
- Google for translation services
