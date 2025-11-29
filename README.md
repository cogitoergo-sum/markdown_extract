# Markdown Extract

A Simple Python library to parse Markdown files from headers.

## Installation

Clone the repository and install the package (or just use the `markdown_extract` folder).

## Usage

```python
from markdown_extract import MarkdownExtractor

markdown_content = """
# Section 1
Some content here.

## Subsection 1.1
More details.
"""

extractor = MarkdownExtractor(markdown_content)

# Get all content under "Section 1" (including subsections)
section_1 = extractor.get_section("Section 1")
print(section_1)

# Get content specifically under "Subsection 1.1"
subsection = extractor.get_section("Section 1", "Subsection 1.1")
print(subsection)

# You can also use bracket syntax to access sections
# This returns a Section object, which can be converted to string
section_1_bracket = extractor["Section 1"]
print(section_1_bracket)

# Chain brackets to access nested sections
subsection_bracket = extractor["Section 1"]["Subsection 1.1"]
print(subsection_bracket)
```

## Features

- Parses nested Markdown headers.
- Retrieves raw content for any specific section hierarchy.
- Preserves structure when retrieving higher-level sections.
