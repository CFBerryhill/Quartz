---
Title: "{{title}}"
Authors: " {{authors}}"
Date Published: 
Date found: "{{date}}"
Keywords: 
Link: "{{pdfZoteroLink}}"
DOI: "{{DOI}}"
Read status: 
Draft:
---
---
year: {{date | format ("YYYY")}}
authors: {{authors}}
abstract: {{abstractNote}}

--- 

### {{title}}
# Data
## Abstract
{{abstractNote}}
## Links

{{pdfZoteroLink}}
## Status: 

# Notes

## Related Papers


{% endif %}{% endfor -%}
