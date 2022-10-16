# WARNING

This scraper gets detected by the server and you will get bolcked.

DO NOT try on public networks to avoid blocking your IP.

Use on Google Colab is recommended. Feel free to make a copy of the same code available at [this link](https://colab.research.google.com/drive/1NvJcmX3_mf_t4DMrBlQd7WigwI-6YQpU?usp=sharing) for use.

# Limitations

1.  The server detects activities. Continuous scraping or scrapning data for an author with more than a couple of hundred publications throws erros. As a temporary solution, the partial results are saved into a json file and are later loaded to try and scrape the remaining data. The following solutions did not work:

- Using sleep between requests.
- Using proxies (due to connection challenges).

2.  The returned HTML sometimes does not contain some of the details (marked with a #TODO comment). As of October, 2022, these details include the link to the publication, the paper description, and the link to the author's photo.

# Google Scholar Scraper

1.  Set the AUTHORID variable in the following.
2.  If on Google Colab, mount your Google Drive.
3.  Define your DATA_PATH variable.
4.  Create your author object using:

```
author_obj = create_author(AUTHORID)
```

5.  Scrape the data about the author using:

```
author_obj.scrape()
```

6.  To see if all publications details are retrieved, check:

```
author_obj.all_publications_extracted
```

7.  If the previous step gives you False, run:

```
author_obj.scrape()
```

The data will be saved as json files in your DATA_PATH. If you are trying to re-scrape data on an author from scratch, destroy the json file named AUTHORID.json before creating the author_object again.
