# ScoreBoy

Score boy lets you easily generate "scores" for work to be done against a codebase, based on the number of results from executing a particular command. You just populate a CSV file with things to check, and ScoreBoy will take care of the rest - populating your CSV with the score ranges and results found in a github gist. 

```
bin/scoreboy ~/docs/quote.csv ~/projects/shipping_lib
```

## Requirements

- we recommend `the_silver_searcher` (https://github.com/ggreer/the_silver_searcher) for working against codebases quickly
- `gist` is used to create github gists of command output. `gem install gist` and then run `gist --login`
- make sure your CSV file has the required headers: `title,check_command,min_score_per,max_score_per,check_result_url,check_result_count,sum_result_score_range` (see template.csv)
- all required columns need to be filled in, except min/max (which default to 1,2 respectivly) and any column with `result` in the name is computed.