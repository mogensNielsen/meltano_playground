# README

## Process

1. Created and activated virtual environment
2. Installed pipx `pip install pipx`
3. Installed meltano `pipx install meltano`
4. Added meltano to path `$env:path = 'C:\Users\mogen\.local\bin;' + $env:path`
5. Initialized project `meltano init .`
6. Activated dev environment `$env:MELTANO_ENVIRONMENT="dev"`
7. Add extractor for csv files `meltano add extractor tap-spreadsheets-anywhere`
8. Add loader for jsonl `meltano add loader target-jsonl`
9. Configures extractor and loader in `meltano.yml`
10. Test by running `meltano run tap-csv target-jsonl`
    - Confirm that the data is written to as configured in `meltano.yml`
11. Adds DuckDB target `meltano add loader target-duckdb`

## Status

The Rick and Morty data is all loaded to the default_schema. I can't get schema_mapping to work.

## Remember

It seems that I have to activate the dev environment before I run any commands `$env:MELTANO_ENVIRONMENT="dev"`

Because the directory `.meltano` is not included in the repository (included in `.gitignore`), one has to install the extractors and loaders when one clones the repository.

## Notes

The extractor `tap-csv` now works with both `target-jsonl` and `target-duckdb`. Use the notebook `query_duckdb.ipynb` to query the DuckDB database file that `target-duckdb` creates.

The CSV files have to have `,` as a delimiter. Otherwise it doesn't work. This is because `tap-csv` doesn't have a configuration for delimiter.

I have now implemented `tap-spreadsheets-anywhere` as it supports `;` as a delimiter. The source files now have `;` as a delimiter.
