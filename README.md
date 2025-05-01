# website-regexscraper-api
🚀 300 Free reqs/mo – Our [Website RegExScraper API](https://rapidapi.com/mohamadabdlrahman03/api/website-regexscraper-api/playground/apiendpoint_beb07fdb-f259-4e1a-9665-6d5ff188457c) extracts text, images, emails, phone numbers, and social links from any website. Perfect for developers building data tools or businesses gathering leads—fast, accurate, and free to start.

# Introduction

Why spend hours building complex scrapers when one API call can grab exactly the data you want? RegExScraper lets you extract multiple data patterns simultaneously from any webpage using the power of regular expressions.

# **🚀Before Getting Started**

### **Regular Expressions in JSON: Important Tips**

When using RegExScraper's POST endpoint, you'll be required to define regular expressions (regex) in a JSON format. It's important to note that JSON requires certain characters, like backslashes and forward slashes, to be **escaped** properly for correct parsing.

#### **Escape Special Characters Correctly**

To ensure your regular expressions work as expected, you need to escape special characters in your regex pattern. Here's what you need to do:

- **Forward Slashes**: In JSON, you need to escape slashes with `\\/`. For example:
  - **Incorrect**: `/images/`
  - **Correct**: `\\/images\\/`

- **Backslashes**: Since JSON uses backslashes for escaping, you'll need to use **double backslashes** (`\\`) for each backslash in your regular expression. For example:
  - **Incorrect**: `\d+`
  - **Correct**: `\\d+`

#### **Correct Example** (Escaped for JSON):

Here's an example of how to correctly write your regular expressions in JSON format:

```json
{
  "url": "https://www.codester.com/items/49579/qrgen-powerful-php-qr-code-generation-script",
  "regex": {
    "images": "https?:\\/\\/[^\\s]+\\.(?:png|jpg|jpeg|gif|webp)",
    "download_links": "(https?:\\/\\/[^\\s]+download[^\\s]+)"
  }
}
```

In the above example, the slashes and backslashes are properly escaped to comply with JSON format.

### **Common Mistakes to Avoid**:
- **Not Escaping Slashes**: JSON requires forward slashes (/) to be escaped as `\\/`.
- **Single Backslashes**: Don't use single backslashes (`\`) in your regex patterns. Always use double backslashes (`\\`) when specifying patterns in JSON.

# 🔍 API Endpoints

## 1. POST Endpoint: Custom Regex Extraction

Use our POST endpoint when you need to extract specific patterns using custom regular expressions.

**Endpoint**: `POST /api/regex-extract`

**Request Body**:
```json
{
  "url": "https://example.com",
  "regex": {
    "prices": "\\$\\d+\\.\\d{2}",
    "productNames": "<h2>(.*?)</h2>",
    "inStock": "In Stock|Available Now"
  }
}
```

**Response**:
```json
{
  "url": "https://example.com",
  "data": {
    "prices": ["$19.99", "$24.95", "$129.00"],
    "productNames": ["Premium Widget", "Ultra Gadget", "Deluxe Tool"],
    "inStock": ["In Stock", "Available Now"]
  }
}
```

## 2. GET Endpoint: Standard Data Extraction

Use our GET endpoint for quick access to commonly needed data without specifying regex patterns.

**Endpoint**: `GET /api/content?url=https://example.com`

**Response**:
```json
{
  "url": "https://example.com",
  "metadata": {
    "title": "Example Website - Home Page"
  },
  "text": "Welcome to Example Website. We offer premium products...",
  "imageUrls": [
    "https://example.com/images/product1.jpg",
    "https://example.com/images/banner.png"
  ],
  "emails": ["contact@example.com", "support@example.com"],
  "phones": ["+1 (123) 456-7890", "800-555-1234"],
  "socialLinks": [
    "https://facebook.com/examplepage",
    "https://twitter.com/examplehandle",
    "https://instagram.com/exampleprofile"
  ]
}
```

## 💰 Save Development Time & Money
No more building custom scrapers for each project. One versatile API handles all your data extraction needs!

## 🎯 Perfect Match Every Time
Pull exactly what matters to you:
- **Product Prices** - Monitor competitor pricing in real-time
- **Contact Information** - Generate targeted lead lists
- **Image URLs** - Build content collections automatically
- **Product Descriptions** - Track market positioning
- **Social Media Links** - Expand your outreach strategy
- **Custom Text Patterns** - You define it, we find it!

## ✨ The Multi-Pattern Advantage
**Why RegExScraper outperforms other APIs:**
- Extract MULTIPLE data types in ONE request
- Name your patterns for organized results
- Process ANY website - from simple blogs to complex ecommerce
- Choose between custom regex patterns (POST) or standard data extraction (GET)
- 🎉 Enjoy 300 free requests per month!

## 🚀 Real Business Applications:
- **Ecommerce**: Track competitor prices across multiple sites
- **Marketing**: Generate leads from business directories
- **Research**: Collect structured data from public records
- **Content**: Aggregate articles from various news sources
- **SEO**: Monitor keyword usage across competitor sites

## 📊 Sample Use Cases:

### Custom Pattern Extraction (POST)
Need to track product details across competitor websites? One API call extracts prices, product names, stock status, and reviews simultaneously.

```json
{
  "url": "https://competitor-site.com/products",
  "regex": {
    "prices": "\\$\\d+\\.\\d{2}",
    "productNames": "<h2>(.*?)</h2>",
    "inStock": "In Stock|Available Now",
    "reviewScores": "\\d\\.\\d out of 5 stars"
  }
}
```

### Quick Contact Information (GET)
Need all contact information from a business website? Use the GET endpoint to quickly extract emails, phone numbers, and social media profiles without writing regex patterns.

## 🔄 Ready To Use In Minutes
- Simple JSON request/response format
- Support for both custom patterns (POST) and standard extraction (GET)
- Comprehensive documentation with pattern examples
- Code samples for JavaScript, Python, PHP, and more

## 💡 Start Finding Exactly What You Need Today!
Why build your own scraper when RegExScraper already does exactly what you need? Save development time and start extracting valuable data immediately!

## Other Tools You Might Like

✅ [🎬 YouTube Scraper Pro](https://apify.com/dz_omar/youtube-scraper-pro) — Extract videos, shorts, live streams, and channel data from YouTube.

✅ [📸 Ultimate Screenshot](https://apify.com/dz_omar/ultimate-screenshot) — Capture website screenshots, PDFs, GIFs, or MP4 videos across different devices.

✅ [📝 YouTube Transcript Extractor](https://apify.com/dz_omar/youtube-transcript-extractor) — Download full transcripts with timestamps and video stats from YouTube.
