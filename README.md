# action-test-general
General file system checks for Pull Requests.

## Features

- Checks for gitignored files that have been accidentally committed
- Detects git conflicts in your codebase

## Usage

Example usage in a workflow:

```yaml
name: Test General

on:
  pull_request:
    branches:
      - main
    types: [opened, synchronize, reopened, ready_for_review]

jobs:
  php-tests:
    if: github.event.pull_request.draft == false
    runs-on: ubuntu-latest
    timeout-minutes: 10

    steps:
    - uses: actions/checkout@v4

    - name: Run general tests
      uses: alleyinteractive/action-test-general@v1

```


## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed
recently.

## Credits

This project is actively maintained by [Alley
Interactive](https://github.com/alleyinteractive).

- [Ben Bolton](https://github.com/benpbolton)
- [All Contributors](../../contributors)

## License

The GNU General Public License (GPL) license. Please see [License File](LICENSE)
for more information.⏎
