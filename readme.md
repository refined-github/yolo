# yolo

> Hotfixes for [Refined GitHub](https://github.com/refined-github/refined-github) fetched regularly

In order to address severe issues as quickly as possible, Refined GitHub fetches hotfixes at most every 4 hours (while being used). These are limited to:

- disabling broken features
- adding some CSS
- updating selectors and other strings (currently unused)

## broken-features.csv

List of features to disable until _the current version_ is greater than or equal to the "fix date"

```csv
Feature name,    Issue, Fix date
show-whitespace, 1234,  22.3.4
```

## styles

Per-version CSS files containing style fixes. If an issue hasn't been fixed by the time the next release comes, the related style hotfix must be manually carried over to a new file.

## strings.json

Generally used to replace troublesome selectors, it can replace any string that has been marked as "dynamic", e.g.

```js
select(_`#title span`)
```

Will be replaced if `strings.json` contains:

```json
{
  "#title span": "#new_title a"
}
```

> **Note:** This file uses JSON because character-escaping logic is widely understood and already implemented natively.
