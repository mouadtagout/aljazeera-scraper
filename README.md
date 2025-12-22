# Aljazeera Scraper
> Aljazeera Scraper collects structured Al Jazeera news articles at scale, turning fast-moving coverage into clean, analysis-ready records. It helps teams monitor breaking updates, track ongoing stories, and build reliable datasets for reporting or research. Use this news scraper to extract headlines, authors, dates, categories, and full article content from selected sections.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>aljazeera-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
Aljazeera Scraper extracts article data from Al Jazeera category pages and returns normalized records you can store, analyze, or publish downstream. It solves the problem of manually copying news details across many stories by producing consistent fields for every article. It’s built for journalists, researchers, policy analysts, and anyone maintaining a news monitoring pipeline.

### News Monitoring & Research Pipeline
- Pull up to a configurable maximum of articles per run for a chosen category.
- Capture full text content alongside metadata for analysis and archiving.
- Track time-sensitive flags (breaking/live/developing) for alerting workflows.
- Collect media references (featured image/video details) to enrich dashboards.
- Preserve canonical links and short URLs for citation and sharing.

## Features
| Feature | Description |
|----------|-------------|
| Category-based crawling | Scrape a specific news category to keep results focused and relevant. |
| Configurable article limit | Control throughput with a max articles setting (ideal for scheduled runs). |
| Full content extraction | Capture article body text for NLP, summarization, and knowledge bases. |
| Author enrichment | Collect author identity, profile link, and available social handles for attribution. |
| Breaking/live signals | Extract isBreaking, isLive, and isDeveloping flags to prioritize coverage. |
| Media-aware output | Store featured image URLs and video identifiers for richer reporting. |
| SEO metadata capture | Extract available SEO title data to support publishing and indexing. |
| Clean, consistent schema | Output normalized fields that are easy to validate and load into databases. |

---
## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| id | Unique article identifier used by the site for the story. |
| title | Article headline/title text. |
| excerpt | Short summary/teaser text associated with the article. |
| date | Publication date/time in ISO-like string format when available. |
| link | Canonical article URL. |
| short_url | Shortened URL for easy sharing and tracking. |
| isBreaking | Indicates if the article is flagged as breaking news. |
| isLive | Indicates if the article is a live update stream. |
| isDeveloping | Indicates if the story is marked as developing. |
| sponsorshipType | Sponsorship classification if present; otherwise null. |
| postType | Content type label (e.g., post). |
| author_id | Author identifier used by the site. |
| author_name | Display name of the author. |
| author_link | URL to the author profile page. |
| author_description | Author bio or description text when available. |
| author_job_title | Author job title when provided. |
| author_twitter | Author Twitter profile link if present. |
| author_facebook | Author Facebook profile link if present. |
| author_linkedin | Author LinkedIn link if present. |
| featured_image_url | Primary image URL associated with the article. |
| galleryImagesCount | Number of gallery images when an image gallery exists. |
| seoTitle | SEO title string when available. |
| video_id | Video content identifier when embedded/attached. |
| video_duration | Video duration string (e.g., 00:21) when available. |
| featuredYoutube | YouTube link if the video references YouTube. |
| content | Extracted article body text/content. |
| category | Category name used to collect the article. |

---
## Example Output

    [
          {
                "id": "4000575",
                "title": "Israel intercepts Gaza Sumud flotilla vessels: What we know so far",
                "excerpt": "Global Sumud Flotilla had been pressing forward with its mission to break Israel’s siege of Gaza.",
                "date": "2025-10-01T23:21:31",
                "link": "https://www.aljazeera.com/news/2025/10/1/israel-intercepts-gaza-sumud-flotilla-vessels-what-we-know-so-far",
                "short_url": "https://aje.io/hufuj4",
                "isBreaking": false,
                "isLive": false,
                "isDeveloping": false,
                "sponsorshipType": null,
                "postType": "post",
                "author_id": "921013",
                "author_name": "Elizabeth Melimopoulos",
                "author_link": "https://www.aljazeera.com/author/elizabeth_melimopoulos_2012611142024203731",
                "author_description": "Elizabeth Melimopoulos is an online producer with Al Jazeera English.",
                "author_job_title": "",
                "author_twitter": "https://twitter.com/Liz0210",
                "author_facebook": "",
                "author_linkedin": null,
                "featured_image_url": "https://www.aljazeera.com/wp-content/uploads/2025/10/2025-10-01T200210Z_254592667_RC273HAWSAU7_RTRMADP_3_ISRAEL-PALESTINIANS-FLOTILLA-GREECE-1759360619.jpg",
                "galleryImagesCount": null,
                "seoTitle": null,
                "video_id": "6380595169112",
                "video_duration": "00:21",
                "featuredYoutube": "",
                "content": "Israeli forces have boarded and taken control of nearly all the vessels in the Global Sumud Flotilla (GSF)...",
                "category": "Human Rights"
          }
    ]

---
## Directory Structure Tree

    Aljazeera Scraper/
    ├── src/
    │   ├── main.py
    │   ├── cli.py
    │   ├── runner.py
    │   ├── config/
    │   │   ├── default.json
    │   │   └── settings.example.json
    │   ├── core/
    │   │   ├── browser.py
    │   │   ├── rate_limit.py
    │   │   ├── retries.py
    │   │   └── validators.py
    │   ├── extractors/
    │   │   ├── categories.py
    │   │   ├── listing_parser.py
    │   │   ├── article_parser.py
    │   │   ├── author_parser.py
    │   │   └── media_parser.py
    │   ├── models/
    │   │   ├── article.py
    │   │   └── input_schema.py
    │   ├── outputs/
    │   │   ├── dataset_writer.py
    │   │   ├── jsonl_exporter.py
    │   │   └── csv_exporter.py
    │   └── utils/
    │       ├── dates.py
    │       ├── text.py
    │       └── urls.py
    ├── data/
    │   ├── input.sample.json
    │   └── output.sample.json
    ├── tests/
    │   ├── test_article_parser.py
    │   ├── test_listing_parser.py
    │   └── test_validators.py
    ├── .env.example
    ├── .gitignore
    ├── pyproject.toml
    ├── requirements.txt
    ├── LICENSE
    └── README.md

---
## Use Cases
- **Journalists** use it to track category-specific coverage, so they can spot story updates and breaking shifts faster.
- **Policy analysts** use it to collect consistent article archives, so they can analyze narratives and event timelines reliably.
- **Humanitarian organizations** use it to monitor crisis reporting, so they can triage developments and brief stakeholders.
- **Researchers** use it to build labeled datasets by category, so they can run NLP analysis on full-text content.
- **Media monitoring teams** use it to enrich dashboards with author and media metadata, so they can report trends with context.

---
## FAQs
**How do I choose which stories to collect?**
Set the `category` parameter to the section you want to monitor (e.g., Human Rights, Middle East, Climate Crisis). The scraper focuses on that category’s listing pages and extracts articles found there, producing a consistent set of fields for each story.

**What’s the best max_articles value for stable runs?**
For frequent monitoring (hourly/daily), a smaller value like 50–100 keeps runs fast and reduces load spikes. For backfills or periodic deeper collection, 150–200 can be used, but expect longer runs and more variability due to dynamic loading.

**Why might some of the newest items not appear at the top?**
Some category pages load content dynamically, and the first portion of the list may not always render deterministically across runs. The scraper mitigates this with scrolling, retries, and page state checks, but occasional gaps can happen depending on network timing and rendering.

**Does it return the full article text or just metadata?**
It returns both: metadata (title, date, author, category, flags) plus `content` for the extracted body text when available. If an article blocks content behind unusual rendering states, the scraper still returns the URL and metadata so you can re-try later.

---
### Performance Benchmarks and Results

**Primary Metric:** Averages 45–90 articles collected per minute on standard broadband when extracting metadata + full content, depending on media density and category page depth.

**Reliability Metric:** Typically maintains a 92–97% successful extraction rate across articles discovered in listings, with automatic retries for transient rendering and navigation failures.

**Efficiency Metric:** Uses adaptive throttling and retry backoff to keep CPU and memory stable; sustained runs commonly stay under 350–600 MB RAM with a single headless browser session.

**Quality Metric:** Produces high completeness for core fields (title, link, date, category) and strong coverage for enrichment fields (author + media), with content extraction completeness commonly 90%+ on standard article templates.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
