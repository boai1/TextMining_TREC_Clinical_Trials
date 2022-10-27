# TextMining_TREC_Clinical_Trials

## Query by document
Query by document (QBD) retrieval is a task in which the user enters a text document – instead of few keywords
– as a query, and the IR engine finds relevant documents from a text corpus. Examples are patent prior art
search and related scientific paper retrieval.

## TREC 2021 Clinical Trials Track
The TREC 2021 Clinical Trials Track is a QBD task
focused at finding clinical trials that are eligible for a specific patient. Patient-related data is provided as a query
in the form of an admission note. Each query contains conditions and observations that describe a patient, and
queries are generally longer than those used in traditional ad-hoc retrieval tasks.


## Dataset 
There are 375, 580 documents, 75 queries and about 11k relevance judgements
 in the Clinical Trial Track collection. Please note that you need to first install ‘ir_datasets’ library in
Python with ‘pip install ir-datasets’ command to be able to download the dataset by ir-dataset library. Queries
are provided in the following format “query_id \t query_content”2. Relevance judgements are available in the
qrels format.


## Objective
### Retrieval and ranking: 
First retrieve 10, 000 (10k) documents given a query by the default
similarity function of Elasticsearch and then re-compute the similarity score on the all 10k candidate
documents based on the variant equation.

### Enable term vector in mapping: 
To be able to compute the variant scores one needs to have access to
the statistical values for each term in the query and candidate documents (e.g. the document frequency
for a term of query in the collection). For this purpose, one needs to enable ‘term_vector’ in the mapping
of your index to be able to get that statistical information of terms. 

## Summary of tasks:
- Do a first-stage retrieval run for the Clinical Trials Track queries with the default ElasticSearch retrieval
function.
- Implement two BM25 variants ranking functions for the Clinical Trials Track task.
