Github Most Popular Repos

Project Overview

This project processes JSON data containing information about the top-starred repositories on GitHub for various search terms. The goal is to extract relevant insights and store them in a PostgreSQL database using Apache Spark.

Resources

Input: An archive file containing 30 JSON files.

Source Data: Available on Kaggle - Top 1000 GitHub Repositories for Multiple Domains

Tools Used:

Apache Spark for data processing

PostgreSQL for storing extracted data

Requirements & Implementation

The project involves extracting three main pieces of information from the JSON files and saving them into structured tables in PostgreSQL:

Programming Languages Table (programming_lang)

Columns:

language: The name of the programming language.

repo_count: The number of repositories using this language.

Implementation: Parsed JSON files to count occurrences of each language and stored the results in this table.

Organizations Stars Table (organizations_stars)

Columns:

organization_name: The name of the organization.

total_stars: The total number of stars across all repositories owned by the organization.

Implementation: Aggregated star counts per organization and stored the results in this table.

Search Terms Relevance Table (search_terms_relevance)

Columns:

search_term: The name of the JSON file (representing the search term used).

relevance_score: A calculated metric representing the overall relevance of repos in that search term.

Relevance Formula:

relevance_score = 1.5 * forks + 1.32 * subscribers + 1.04 * stars

Implementation: Applied the formula on extracted data and stored results in this table.

Key Deliverables

Apache Spark code for processing JSON files and saving output to PostgreSQL.

A PostgreSQL database containing the extracted and structured data.



