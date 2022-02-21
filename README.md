# homebrew-strictdoc

This repository provides `strictdoc` as a `brew` package. To install
`stricdoc` execute the following statements in the terminal:

```
brew tap fkromer/homebrew-strictdoc
brew install strictdoc
```

## Development

To create a `brew` formula one cannot setup the `venv` using poetry cause
[`poetry` does not allow to install strictdoc in development mode yet](https://github.com/python-poetry/poetry/issues/34).
[Create and activate a `venv` the plain Python way](https://docs.python.org/3/tutorial/venv.html#creating-virtual-environments) instead.

```
python3 -m venv venv-strictdoc-homebrew
source venv-strictdoc-homebrew/bin/activate
```

Install `brew` on Mac OS or Linux (on Linux into `/home/linuxbrew/.linuxbrew/bin/brew`) like [described on the website](https://brew.sh/).

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Install `strictdoc` and the homebrew helper `poet` for generating Python formulas into the `venv`:

    pip install strictdoc homebrew-pypi-poet

Generate the Homebrew formula for `strictdoc` including it's dependencies and leave the `venv`:

    poet -f strictdoc > Formula/strictdoc.rb
    deactivate

Adjust the content of `Formula/strictdoc.rb`.
