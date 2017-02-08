---
layout: lesson
root: .
title: Working with Open Refine
minutes: 
---

# Lesson

## Saving and Exporting a Project

In OpenRefine you can save or export the project. This means you're saving the data and all the 
information about the cleaing steps you've done. Once you've saved a Project, you can
open it up again and be just where you left off.

### Saving

By default OpenRefine is saving your project. If you close OpenRefine and open it up again,
you'll see a list of your projects. You can click on any one of them to open it up again.

### Exporting your project

You can export a project, for instance if you wanted to send it to someone else, or put it under version control.

## Exporting Cleaned Data 

Export your cleaned data when you are done by exporting it in the desired format. Save your files with meaningful names, no spaces. Refine does not change your original dataset (hooray!). Let's look at the many formats Open Refine can produce:

  * TSV / CSV file (good for data exchange / preservation)
  * Excel / Open/Libre Office
  * Linked Open Data eg RDF triples
  * Custom tabular (note you can save Option code for automation)
  * Custom template

### Practice
  - Go to the 'Export' button in the top right. Click 'Export project'. This will save a compressed file that you can then open in OpenRefine that contains all the data and steps. Try opening new Open Refine tab and importing this project. You can close the tab once you've confirmed it works.
- Use the custom tabular exporter to export the columns 'survey_id', 'recordID' and 'species' in TSV format, ensuring the 'recordID' is the first (ie leftmost) column. View these in a text editor (or use ```cat somefile.tsv``` in bash to check the output.
- Put up a green sticker when you're done.


Previous: [Scripts](02-scripts.html) Optional Next: [Services in OpenRefine](04-services.html)
