The following redesign will hopefully make the experience of starting with computing as painfree as possible for students, with having them focus on what is most important at the appropriate stage


### Infrastructure configuration

All of the content and assignments for the course: lecture slides, problem set questions, lab questions, and lab slides are hosted on the course website in polished html form. The source for materials themselves should live in a `stat20-materials` repo that is linked from the course website but not shown to students. The course website itself can be hosted out of a `stat20-website` repo.

Students benefit from not having to create brand new Rmd files for their assignments, particularly in the beginning. One option is to use `nbgitpuller` to sync with a repo that we manage that gives them a `problem-sets` and `labs` directories that we can populate with template Rmds. The other option is to keep those templates in an R package that we pre-install on the server.

I'd opt for the latter. nbgitpuller probably seems like some black magic to students (the files just appear!) while they'll be familiar with creating new documents and saving them. It'd also save us the work from having to dribble out the template Rmds to the synced repo and continually asking the students to sync. Best if these templates loaded all of the packages needed for the labs so that we can put an `message = FALSE` option on it and never have to talk with the students about r chunk options (or can at least delay the conversation).

Teaching guides for the labs can live as presenter notes in the Rmds of the lab slides hosted in `stat20-materials`, so there should be no need for a separate `teaching-guide` repo.

### Management of branches

Both the `stat20-materials` and `stat20-website` repos can each use three branches.

1. `dev`: where new changes are proposed for the current semester (changing slides, changing assignments). PRs are made into `main` prior to materials being published
2. `main`: the official source of the materials hosted on the course website.
3. `next-semester`: kept downstream from `main` as a place to make revisions to materials as soon as they are taught in the current semester (and before we forget).

At the end of the semester, the last commit on `main` is tagged as the official documentation of the course that semester. `next-semester` makes a PR into `main`, and `dev` is made a fresh branch off of `main`.

What's the best way to publish html files from `stat20-materials` into `stat20-website`? We could write an R package with functions to do the appropriate copying and modifying of `stat20-website` source. Those functions could either be called manually or via scheduled GitHub actions on the `stat20-website` repo.


### Student journey

1. First teach markdown as a replacement for Word.
2. Then teach R at the console as a replacement for a calculator / excel.
3. Third teach Rmds with markdown + R as a way to combine the two in a manner that is reproducible.

### Progression of assignments

**Markdown**

1. Students first see Rstudio in lecture as a way to write their first assignment. They're not shown how to access it, just what it generally looks like and how it can be used like Word.
1. In lab students are
    i. shown slides (not demo'ed) of the following elements, using screenshots from a DataHub.
    - The four panels of RStudio, with a focus for now on files and editor.
    - How to create and save a new problem set Rmd from a template.
    - How to knit to pdf, where the pdf shows up, and what the conceptual link is between source and final product.
    - Header vs Markdown
    - In the header, the following fields
        - title
        - author
        - output
    - In the markdown
        - normal text
        - headings
        - bold and italics
        - bulleted list
    ii. then left on their own to create their own document that answers a few questions (those question will show up only on the website as an html document).

**R**

1. Lecture: Students first see R as an improved calculator with just a few commands issued to the interpreter: 
    - 1 + 3 # arithmetic
    - a <- 1 + 3 # save results
    - a # print object
    - sqrt(a) # math function on an object
    - library(stat20data) # load library with messages
    - data(classdata) # silently load data
    - classdata # print data to console
    - arrange(classdata) # function on df
    - arrange(classdata, var) # multiple args
    - arrange(classdata, desc(var)) # function inside a function is ok
1. Lab: students
    - Follow along with slides that introduce each new function and then give them a chance to try at the console. This iterates back and forth, with the students generating output that can be copy-and-pasted into a Word document: basic summary statistics and simple plots (copyied to clipboard using the IDE), preferrably all just a single line of code.
    - Students submit to gradescope a word document
    
**RMarkdown**

1. Lecture: students are talked through the Rogoff and Reinhardt affair and walked into the conundrum that it seems that our workflow suffers from the same problem of irreproducibility. RMarkdown is presented as a solution and demo'ed.
1. Lab: students work on the arbuthnot lab. Start off with slides only; not showing the students the questions.
    - The current slides are added on to replace the instruction portion of the first three questions. Each "try this" command is issued in a slide, then students do it at the console to try it out.
    - After maybe the first two questions are gone through, the GSI goes to the website to fetch the questions for the lab and demos opening up a new Rmd lab template and copying in the code that she sent to the console previously, knitting often.
    - Students are set loose to work on remaining problems, coming back together towards the end of the period.

