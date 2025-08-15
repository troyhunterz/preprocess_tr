# Text Preprocessing Python Package
This python package is created by [anonfolder](testfolder.com). It provides various text preprcoessing utilities for natural language processing (NLP) tasks

## Installation
### Installation from Pypi
You can install this package using pip as follows:
```console
pip install preprocess_tr
```

### Installation from GitHub
If you want to install via github:
```console
git clone https://github.com/troyhunterz/preprocess_tr
```

## Requirements
You need to install this python packages:
```console
pip install spacy==3.8.5
pip install -m spacy download en_core_web_md==3.8.0
pip install nltk==3.9.1
pip install beautifulsoup4==3.2.2
pip install textlob==0.19.0
```

### Download NLTK Data
If you are using this package first time, then you need to download NLTK data as follows:
```python
import preprocess_tr as ps
ps.download_nltk_pkgs
```

## Uninstall the Package
To uninstall the package, use the following command:
```console
pip uninstall preprocess_tr
```

## How to Use the Package
### Full Example: Cleaning Text
Here's an example of how you might use several functions together to clean text data:
```python
import preprocess_tr as ps
def clean_text(text):
    text = ps.to_lower_case(text)
    text = ps.contraction_to_expansion(text)
    text = ps.remove_emails(text)
    text = ps.remove_urls(text)
    text = ps.rm_html(text)
    text = ps.rm_special_chars(text)
    text = ps.lemmatize(text)
    return text

text = "I'm loving this NLP tutorial! Contact me at example@example.com. Visit https://example.com."
cleaned_text = clean_text(text)
print(cleaned_text)
# Output: i am loving this nlp tutorial contact me at visit
```

### One Short Feature Extraction
```python
import preprocess_tr as ps
ps.extract_features('i love NLP')
```

## Notes
* Be cautious when using heavy operations like lemmatize and spelling_correction on very large datasets, as they can be time-consuming
* The package supports custom cleaning and preprocessing pipeline bby using these modular functions together
