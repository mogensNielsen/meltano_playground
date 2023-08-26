# README

## Process

1. Created and activated virtual environment
2. Installed pipx `pip install pipx`
3. Installed meltano `pipx meltano`
4. Added meltano to path `$env:path = 'C:\Users\mogen\.local\bin;' + $env:path`
5. Initialized project `meltano init .`
6. Activated dev environment `$env:MELTANO_ENVIRONMENT="dev"`
7. Add extractor for csv files `meltano add extractor tap-csv`
8. Add loader for jsonl `meltano add loader target-jsonl`
9. Configures extractor and loader in `meltano.yml`
10. Test by running `meltano run tap-csv target-jsonl`
    - Confirm that the data is written to as configured in `meltano.yml`

## Notes

Because the directory `.meltano` is not included in the repository (included in `.gitignore`), one has to install the extractors and loaders when one clones the repository.

I have moved 