## Scraper Challenge Data Science / Python

We want to analyse the prices of books and how they change over time.

Therefore, we want to scrape the site http://books.toscrape.com/index.html and store information about the found books in a database. To be more rpecise, we want to know the category a book is in, its title as well as the current price.

### The challenge 

Write a script that scrapes books from a set of categories that can be specified. It should store the information in a SQLite database. The script should be designed in a way that it could run e.g. as a cron for daily execution.

If you want an additional difficulty, you can try to find a way to also get the author of the book since the crawled site does not contain this information.

### First Steps

If you've never build a web crawler before, you might want to search for a tutorial explaining the basics of it. Technologies that can be used are the [Selenium browser](https://pypi.org/project/selenium/) and [Beautiful Soup](https://pypi.org/project/beautifulsoup4/). But there are many alternatives out there, so use whatever you find the best fit.

### Additional Requirements

To be able to run this on our end, it has to be able to run on
- the latest Ubuntu distros
- either Firefox or Chrome
- Python packages that are available on PyPI
