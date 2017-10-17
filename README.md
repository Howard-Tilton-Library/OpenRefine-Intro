# OpenRefine-Intro
Wrangling Data with OpenRefine. - Room 602 Howard-Tilton Library

This will be a short show and tell on using OpenRefine to edit “messy” data. Bringing your laptop with [OpenRefine](http://openrefine.org/download.html) pre-downloaded and your own messy data is recommended.
Attendees will learn how faceting, sorting, and clustering data can help create cleaner data sets for other uses. They will also see one example of the use of Linked Data/Sparkle endpoints in controlling and cleaning data.
Audience: Senior undergraduates, graduate students, lab assistants, staff, and faculty

## Getting Started
How to install OpenRefine: https://github.com/OpenRefine/OpenRefine/wiki/Installation-Instructions
How to prepare your computer to use RDF reconciliations: http://refine.deri.ie/installationDocs

## Beginning a Project
### To create a project 
* Double click openrefine.exe where you saved it on your computer
* A command line box will open and the GUI will open in your default browser
* Select "Create Project" on the left and the location of a project 
  * Select the appropriate type of file to parse data as
  * Experiment with options within that type (character encoding, rows to discard or store)
  * review the preview to make sure your data is being parsed correctly
  * select "Create Project>>>" at the top and wait
  * when the project opens, scroll through some of the rows/pages and double check your parsing settings worked
### To exit the program
* CTRL + C will close the command line and stop the program (even if it's still open in your browser)
### To open a project
* Start OpenRefine up again
* Now select "Open Project" to work on the project you've previously created

For another option, see import project below.

## Review your Data
### Faceting
* Use the dropdown menu on a field (like 100) to "Facet>Text facet"
* On the left you can now see the contents of the field, how often those contents repeat, and you can sort

### Edit cells
* Sometimes you will want to edit the contents of a field based on what you see in the facet
* To get the names and dates without author or illustrator at the end, try "Edit cells>Transform..." and then the GREL chomp(value, 'illustrator.')
* Repeat this step, editing the GREL as necessary until you don't have any roles in this column
* Did you notice anything unexpected in your results?
* Some trial and error or experimentation will be necessary

### Edit column
* Edit column>Split into several columns (change delimiter to ';')
* Re-facet resulting columns
* What do you see?
* Use the same technique on the 300 until pages, types of materials, and size of materials are all in their own column (can be done with regex)
* If you mess up, go to "Undo/Redo" at the top of the left column, and select the nearest step before your mistake, then return to "Facet/Filter" and try again

### Clustering
* Find the appropriate box in the lefthand column to see all the sizes available
* Select "Cluster" in the box or on that column select "Edit cells>Cluster and edit..."
* Experiment with your options until you have joined all of the appropriate values
* How have the results in the facet box changed?

### More on GREL (Google Refine Expression Langauge)
* [GREL](https://github.com/OpenRefine/OpenRefine/wiki/Understanding-Expressions) allows you to use regular expressions to edit in OpenRefine 
* create and test your regex in [regular expressions 101](https://regex101.com/)
* test them on 10 of your rows...second row shows value after running
* [Google Refine Cheat Sheets](http://arcadiafalcone.net/GoogleRefineCheatSheets.pdf)
* [Library Carpenty OpenRefine](https://data-lessons.github.io/library-openrefine/07-using-transformations/)

## Ending a project
### To export a project
* Once your project is open, select the export drop down
* Select the appropriate option:
  * tab or comma-separated value will create the most basic result
  * templating allows you to create records for multiple schema using JSON
  * if your columns are aligned with an RDF schema, you can also export triples
  * to share your entire project (not just your data, but the transformations you completed on it), select export project
* If you save and share a project, the recipient will have to open it in OpenRefine
### To import a project
* Select Import Project in the left side of the screen
* Browse and select the file you saved in the last step
* Rename if necessary, and select "Import Project"

## Advanced Options
## Reconciliation
General information about Reconciliation Services in OpenRefine: https://github.com/OpenRefine/OpenRefine/wiki/Reconciliation-Service-API
LCNAF and LCSH reconciliation: https://github.com/cmh2166/lc-reconcile
VIAF reconciliation: http://refine.codefork.com/

* if there is time, help download and run VIAF reconciliation
* if not, just demo on the 100 field
