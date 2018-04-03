# Homework

## Homework 2 UPDATE

The first version of HW2 contained one erroneous test.  The reason for the
error was that in the reference solution we used int16 for POS transition
counts which overflew for some of the transitions. We have corrected this
mistake and added public tests that raise an error if the count matrices
and the probability matricies have negative elements. These changes only affect
Exercise 4 and 5. The instructions did not change, your old solution should
work fine (if it is correct).

If you click on the invitation link **after** April 2, Monday, you will
automatically clone the corrected version.

If you created your own homework repository **before** April 3, you have to
manually pull the changes. If you already have changes in the file (you started
to work on the homework), the easiest way is to copy your existing solution to
a separate file, and reset `homework2.ipynb` before pulling (you do not want to
resolve a merge conflict between Jupyter Notebooks).

We provide instructions of command line interfaces (Linux Terminal, MacOS
Terminal and Powershell):

    cd /path/to/homework2-johnsmith
    cp homework2.ipynb homework2-old.ipynb
    git checkout -- homework2.ipynb

Now you can add the common repository as a new remote, fetch and merge the new
version:

    git remote add python-nlp https://github.com/python-nlp/homework2.git
    git fetch python-nlp
    git merge python-nlp/master

You can copy and paste your old solution into the new notebook.

If you have done everything correctly, the last assert statement should be
this:

    assert tags == ['DT', 'NN', 'VBZ', '.']

## Homework2

This page describes general information regarding the mandatory homeworks for this course.
The actual homeworks are published in the `homeworks/` directory.
Please read the instructions and `README.md` (if available) files for each homework carefully.

## Collaboration

The homeworks are individual assignments.
Collaboration is not prohibited but you are expected to submit your own solution.
You may be required to orally present your solutions.

## Submission

Submissions are managed through Github Classroom. You will receive an invite link via
Neptun.

1. Click on the invite link and login to GitHub. Create an account if necessary.
2. Grant access to GitHub Classroom. It will only use your public information
   and your homework repository's information.
3. Find your name in the course roster and click on it. If you can't find your
   name in the list, please email the instructor.

Now Github Classroom creates your own private repository for this homework with
the starter code (the homework notebook) in it. This may take a few minutes.

If you're unfamilar with git, many great tutorial are available online such as
the Git Book [here](https://git-scm.com/book/en/v2) (Chapter 1 and 2 should be
more than enough for this course).

### Final submission

The last commit in this repository before the deadline will be your submission
for this homework.

Please be aware that we might delete these repositories after the end of the
semester.

### Late and repeated submission

One homework assignment can be (re-)submitted by the end of the repeat period
in accordance with the Code of Studies and Exams.

## Grading

Each homework is graded from 1 to 5.
You are required to achieve the grade 2 for each homework in order to take the final exam.
The scoring system is released along with each homework.

## Summary

All deadlines are Sunday 23:59 PM CET.

| Homework | Release Week | Deadline Week | Person in charge | Email |
| ---- | ---- | ---- | ---- | ---- |
| 1 | 3 | 6 | Judit Acs | judit@aut.bme.hu |
| 2 | 7 | 10 | Judit Acs | judit@aut.bme.hu |
| 3 | 10 | 13 | David Nemeskey | nemeskeyd@gmail.com |

## Help

If you have any questions or general feedback regarding the homeworks, please file a GitHub issue with the `homework` tag.
