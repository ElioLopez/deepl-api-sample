deepl-api-sample
---

These are sample scripts of using DeepL API by Python.

- Runtime: Python 3.x

# Usage

## Preparing

### Create config.json

Create a `config.json` by copying `config.json.sample` .

```bash
$ cp config.json.sample config.json
```

```json
{
  "auth_token": "your-deelpl-api-auth-token"
}
```

## Features

- translate
- monitoring usage

### translate

```bash
$ python3 src/translate.py -h
usage: translate.py [-h] [-m MESSAGE] [-t TARGET] [-s SOURCE]

optional arguments:
  -h, --help            show this help message and exit
  -m MESSAGE, --message MESSAGE
                        text to translate. (Default: Hello World.)
  -t TARGET, --target TARGET
                        target language code (Default: JA). allowed lang code
                        : ['DE', 'EN', 'FR', 'IT', 'JA', 'ES', 'NL', 'PL',
                        'PT-PT', 'PT-BR', 'PT', 'RU', 'ZH']
  -s SOURCE, --source SOURCE
                        source language code (Default: auto). allowed lang
                        code : ['DE', 'EN', 'FR', 'IT', 'JA', 'ES', 'NL',
                        'PL', 'PT', 'RU', 'ZH']
```

#### example

```bash
$ python3 src/translate.py -m "これは DeepL API のサンプルプログラムです。" -t EN
{
  "translations": [
    {
      "detected_source_language": "JA",
      "text": "This is a sample program for the DeepL API."
    }
  ]
}
```

### monitoring usage

```bash
$ python3 src/usage.py
{
  "character_count": 192,
  "character_limit": 1000000
}
```