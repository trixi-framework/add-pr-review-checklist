# Add PR review checklist
GitHub Action for adding a review checklist to newly created pull requests.

## Usage

Add your Markdown-formatted review checklist to your repository, e.g., as
`.github/review-checklist.md`. An example checklist can be found
[here](example-review-checklist.md).

Then, create a file `.github/workflows/ReviewChecklist.yml` with the following content:
```yml
name: Add review checklist

on:
  pull_request_target:
    types: [opened]

jobs:
  add-review-checklist:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v3
      - name: Add review checklist
        uses: sloede/add-pr-review-checklist#main
        with:
          file: .github/review-checklist.md
```

## Author
This repository was initiated by [Michael Schlottke-Lakemper](https://lakemper.eu).

## License
This repository is licensed under the MIT license (see [LICENSE.md](LICENSE.md)).