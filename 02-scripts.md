---
layout: lesson
root: .
title: Automating your work in OpenRefine
minutes: 
---

# Lesson

## Automate your work with scripts

* Refine saves every change, every edit you make to the dataset in a file you can save on your machine.
* If you had 20 files to clean, and they all had the same type of errors, and all files had the same columns, you could save the script, open a new file to clean, paste in the script and run it. Voila, clean data.

### Save a script
  - In the Undo / Redo section, click Extract, save the bits desired using the check boxes. 
  - Copy the code and paste it into a text editor. Save it as a .txt file. 

### Open a new project from scratch
- Right click on the Open Refine logo at top right
- We'll create a new project with our same Rodents data, as just to test how this works.
- But this time we'll create the project from a web address
- Copy the link to the Rodents data stored in Dropbox and paste it into Open Refine but don't click 'Next' yet
- In the URL, replace the 'www' with 'dl', then click Next.
- Create a new project, perhaps named 'More Rodents'?

### Apply saved script
- Now go to the Undo / Redo tab, click 'Apply', and carefully paste in the contents of the saved .txt file, then click Apply.  

## Writing programs within Open Refine

Open Refine becomes even more powerful when you use the programming languages embedded within it. We'll use Python here, since many of you will have used it earlier today

### Add some useful metadata

Let's say we want to work with the locality column, and identify those cells with longer descriptions. 
There's no built in functionality for this, but it is easy if we add some Python (or GREL or Clojure...)

We'll use Edit column > Add column based on this column from the dropdown and enter the following program:

```if len(value) > 30:  
    return True
    ```

We then have a flag, and we can facet the column to get only the longer or shorter localities, using **Facet > Customized facets > Facet by blank**. Facet by blank is also really useful for checking for errors.

### Join data from multiple columns

As another example, we can use a Python program to join the date column from dy, mo, yr. Note: [OpenRefine's wiki](https://github.com/OpenRefine/OpenRefine/wiki) has good documentation for doing this using GREL (Google Refine Expression Language), it's a bit hit and miss for Python or Clojure).

Select the 'mo' - month column

Again, **Edit columns > Add column based on this column...** and enter the following instruction:

```
return cells["dy"]["value"] + "/" + value + "/" + cells["yr"]["value"]
```

Now we have more useful date information.

### Practice

* Let's convert our new date column to be a 'date' datatype
* Now facet the data on the 'date' column using the Timeline facet
* What was the date of the first record in 1978?
* Put up a green sticker when you're done!

Previous: [Working with OpenRefine](01-working-with-openrefine.html)  Next: [Saving and Exporting files and projects](03-save-export.html)
