# Solr Goodread Quotes Search Tool
This project is a Solr-lucene implementation for a search tool that returns Goodread quotes.

# To run
## For Windows:
1. Run `bin\solr start` in project directory
2. Open http://localhost:8983/solr/#/quotes/core-overview

## For Linux/Mac
1. Run `bin/solr start` in project directory
2. Open http://localhost:8983/solr/#/quotes/core-overview

# To stop
## For Windows:
1. Run `bin\solr stop -all` in project directory

## For Linux/Mac
1. Run `bin/solr stop -all` in project directory



# List of important queries in Solr Admin
### Full import
`http://localhost:8983/solr/quotes/dihupdate?command=full-import`

### Delete all documents
1. Select "quotes" core in bottom left of admin page
2. Select Documents
3. Change "Document type" box to "XML"
4. Enter `<delete><query>*:*</query></delete>` in "Document(s)" box

### Query to get everything
`http://localhost:8983/solr/quotes/select?indent=on&q=*:*`

### Query by tags (replace <include_tag_here>)
`http://localhost:8983/solr/quotes/select?q=tag%3A%22<include_tag_here>%22&wt=json`

### Query by author (replace <include_author_here>)
`http://localhost:8983/solr/quotes/select?q=author%3A%22<include_author_here>%22&wt=json`

### Query by quote (replace <include_word_here>)
`http://localhost:8983/solr/quotes/select?q=quote%3A%22<include_word_here>%22&wt=json`

### To show some fields only
Example of showing only quote and author fields:
Add `fl=quote,author` to url parameter

### Sort likes desc
Add `sort=likes%20desc` to url parameter

### Sort likes ascending
Add `sort=likes%20asc` to url parameter

# Important files
Data Config File: `/server/solr/quotes/conf/data-config.xml`
Schema File: `/server/solr/quotes/conf/schema.xml`
Solr Config File: `/server/solr/quotes/conf/solrconfig.xml`
Quotes Data File:`/server/solr/quotes/input/quotes_final.xml`

# Note
- Whenever schema file is updated, remember to delete managed-schema file
