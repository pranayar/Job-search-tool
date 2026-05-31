# LinkedIn Job Search Filter

A lightweight Python script that searches LinkedIn job listings and automatically filters out unwanted roles, companies, and duplicates.

Designed for job seekers who are tired of scrolling through hundreds of irrelevant postings and want to focus only on positions that match their target skill set.

## Features

* Search LinkedIn jobs by keyword and location
* Filter jobs posted within the last 7 days
* Require specific keywords in job titles/company text
* Exclude senior-level positions
* Exclude specific companies
* Remove duplicate postings
* Display results in a clean terminal table
* Easily customizable filtering rules

## Example Use Case

Looking for:

* Software Developer
* .NET Developer
* C# Developer

While automatically excluding:

* Senior Developer
* Lead Developer
* Manager
* Architect
* Principal Engineer
* Director-level roles

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/linkedin-job-search-filter.git
cd linkedin-job-search-filter
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Requirements

```txt
requests
beautifulsoup4
tabulate
```

## Configuration

### Search Keywords

```python
keywords = "software developer OR .NET OR C#"
```

### Search Location

```python
location = "Toronto, Ontario, Canada"
```

### Required Keywords

At least one of these words must appear in the job title or company text:

```python
REQUIRED_WORDS = {
    "developer",
    ".net",
    "c#",
    "software"
}
```

### Excluded Job Titles

Jobs containing any of these terms are skipped:

```python
EXCLUDED_WORDS = {
    "senior",
    "sr.",
    "lead",
    "manager",
    "architect",
    "principal",
    "director",
    "staff",
    "vp"
}
```

### Excluded Companies

Ignore companies you are not interested in:

```python
EXCLUDED_COMPANIES = {
    "Example Company"
}
```

## Usage

Run the script:

```bash
python job_search.py
```

Example output:

```text
+----------------+--------------------+-----------+----------+------------------+
| Company Name   | Job Role           | Location  | Posted   | Job Link         |
+----------------+--------------------+-----------+----------+------------------+
| Company A      | .NET Developer     | Toronto   | 2 days   | https://...      |
| Company B      | Software Developer | Toronto   | 5 days   | https://...      |
+----------------+--------------------+-----------+----------+------------------+

Total jobs found: 12
```

## How It Works

1. Builds a LinkedIn job search URL using your keywords and location.
2. Downloads the public search results page.
3. Parses job cards using BeautifulSoup.
4. Applies custom inclusion and exclusion filters.
5. Removes duplicates.
6. Prints matching opportunities in a formatted table.

## Customization Ideas

* Export results to CSV
* Email notifications
* Daily scheduled searches
* Multiple locations
* Remote-only jobs
* Salary filtering
* Save results to a database
* Discord or Slack notifications

## Disclaimer

This project is intended for educational and personal-use purposes only.

LinkedIn may change its page structure at any time, which can break scraping functionality. Users are responsible for complying with LinkedIn's Terms of Service and applicable laws.

## License

MIT License
