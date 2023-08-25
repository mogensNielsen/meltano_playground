# Process

1. Created and activated virtual environment
2. Installed pipx `pip install pipx`
3. Installed meltano `pipx meltano`
4. Initialized project `meltano init .`
5. Activated dev environment `$env:MELTANO_ENVIRONMENT="dev"`
6. Add extractor for spreadsheets and csv files `meltano add extractor tap-spreadsheets-anywhere`
