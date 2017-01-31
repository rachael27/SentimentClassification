#
Sentiment Analysis Classification using Classical Machine Learning Approaches

#### Step-by-Step Tutorial with R and WEKA

##

## Objective

To provide a hands-on Classification-101 tutorial using R and WEKA.

##

## Overview & Purpose

This tutorial is an introductory guide to classification using R and WEKA. We will first explore the Iris dataset in R and construct a Decision Tree to see the attribute values that are responsible for splitting the tree. We will then use Support Vector Machines \(SVM\) classifier to classify the data.

In the second half of the tutorial, we will classify a set of Tweets based on the sentiments they express - positive or negative. We will perform Feature Extraction and then classify them using some of the various classifiers that are available in WEKA.

##

## Tools & Software Required

1. [R](https://www.r-project.org/)- R is a language and environment used for statistical computing, graphics and machine learning. It can be be downloaded for [Windows](https://cran.r-project.org/mirrors.html) and [Mac](https://cran.r-project.org/bin/macosx/).

2. [R Studio](https://www.rstudio.com/)- It is an IDE for R. It can be downloaded for Windows and Mac [here](https://www.rstudio.com/products/rstudio/download/).

3. [WEKA](http://www.cs.waikato.ac.nz/ml/weka/index.html)- Data Mining softwarethat has tools for data pre-processing, classification, regression, clustering, association rules, and visualization. Weka for Windows and Mac can be downloaded [here](http://www.cs.waikato.ac.nz/ml/weka/downloading.html).

##

## How to read this DIY tutorial document?

This document has been written in such a way that it is easy to follow for a beginner. Here are some tips to get the most out of this document.

1. Entire code scripts, airline dataset along with this document are available on our GitHub account:ArabWICQatar,which can be accessed from this page [https://github.com/ArabWICQatar](https://github.com/ArabWICQatar). These materials will be required for this tutorial. Feel free to “fork”.

2. All commands in the Rstudio prompt are marked with “&gt;”. If you find any line marked with “&gt;”, it is a command that can be typed into the Rstudio console.

3. If you do not have any background to some sections, appropriate references for that section are provided.

4. If any section is marked as“optional”, you can skip them as it won’t affect your understanding of the upcoming sections. But beware, you are missing out on the fun!! :\)

5. You will find certain commands marked as "fun". These have been incorporated to give you a quick break.

We at ArabWic Qatar hope you enjoy this tutorial!

#

# Quick Start with Rstudio

| OPTIONAL: IF you’ve worked with Rstudio before. |
| :--- |


Let’s have a quick look at the Rstudio IDE. It will help you to navigate the IDE faster.

To remember:

* Each piece of code in R is saved with a.R extensionand is called aSCRIPT.

* Commentsin a R script start with the“\#” symbol.

* All commandsin the console start with the “&gt;” symbol.

* Each package that you need for a script should first be installed and then loaded using thelibrarycommand.

* Installation of packages are done only once, however loading of packages are done for every session.

* IF YOUR SESSION RESTARTS, LOAD ALL YOUR PACKAGES ONCE AGAIN!!\(using the library\(NameOfPkg\) command\)

![](https://lh3.googleusercontent.com/NK3UvE4LqANT6c592rzjRrIWqHnIC-hgf_BhSxZK2V6yu4PGv05rmKqd_4qE7phQgMrYoOldJd2jE8S9nxtTZ2BFs74fJSo3HF2lLty8FkcAZj2C2DwuxWJXhpdI9Y587LGW11Q "rstudio.png")

* Code Editor- The place to write your scripts and for viewing data structures using the View command. It contains buttons for running the entire script or for running it line-by-line.

* R Console- You will use it view the output and for executing single-line commands.

* Workspace and History- You will find each variable that you created under the “Workspace” tab and a history of all your commands under the “History” tab.

* Plots and Files- Your one stop for viewing files/plots/installing packages etc.



| FUN: Type “Hello &lt;&lt;Your Name&gt;&gt;” in the RConsole. \(Don’t forget the quotes\).When the greetings are over, proceed to the next section. |
| :--- |


# 3. Phase 1 in R

In this phase we will use the simple and popular IRIS dataset in R. We will run a Decision Tree and SVM classifier on this dataset which is available in R.

### IRIS Dataset

This dataset has the Petal and Sepal, length and width as features for three different types of flowers: Versicolor, Setosa and Virginica.

* We will first examine the dataset in R. For more details about the dataset, type the following command.
`> ?iris`
Output will be shown in thePlots and Filesarea.
Read the file to know more about the IRIS dataset.

* We will now load the dataset, using the next command.
`> data(“iris”)`
You can see that the dataset iris is loaded in theEnvironment and Workspacearea.



* Let us now check the size of the dataset - number of rows and columns.

&gt; nrow\(iris\)
\[1\] 150
&gt; ncol\(iris\)
\[1\] 5



1. Let us now see the first few rows of the dataset, to understand the structure of the dataset. We can see that the dataset is made up of 5 features, namely,Sepal.Length, Sepal.Width, Petal.Length, Petal.Width and Species.

&gt; head\(iris\)

Sepal.Length Sepal.Width Petal.Length Petal.Width Species

1 5.1 3.5 1.4 0.2 setosa

2 4.9 3.0 1.4 0.2 setosa

3 4.7 3.2 1.3 0.2 setosa

4 4.6 3.1 1.5 0.2 setosa

5 5.0 3.6 1.4 0.2 setosa



1. Let us get a summary of all the features \(each column\) in the dataset. This gives us details like minimum,median, maximum values etc. of the features. We can also see there are 50 observations of each flower under the Species tab.

&gt; summary\(iris\)

Output will be shown in theConsole.



1. Now, that we have a general idea of the dataset, let us view the entire dataset.

&gt; View\(iris\)

Output will be shown in theCode Editor.



Your IDE should like the following image, once you are done with all of the commands.

![](https://lh6.googleusercontent.com/ax7jYtKc9mQUzjzF-GKYdzfamXiijmZNjgd2fKXqOhxaG9gicgoAl857tNfRept9pa8E0EvzHjiTctgk4GXK-KzZSUpJa-gUP6FjNayNrcp1M17JqhxXZmnPu_kCNkjhbaOTFUA "Screenshot 2017-01-17 01.07.56.png")



#### Install a package

Let us now install the package“party”for creating adecision tree.

1. In the Menu bar, click onTools -&gt; Install Packages.

2. In the dialog box that appears, typepartyin the packages text box.

This will install the required package along with the dependencies.

3\) Repeat to install package“fun”.

4\) Load the packagefunby typing the following command:

&gt;library\(fun\)



![](https://lh4.googleusercontent.com/zF_HT7Lg_grNEm5fTpu022iTGC4MVcEaAL2OyrkO_bcG3Is2zPQiUhnDT0XdDJkkRUde3ivRVZ3dd2CZssy5SNTQ6Rrk7Ew2CHQ7Na8XgRd1BNcnw77KKpG0x02vnnA62DhPOnQ "Screenshot 2017-01-17 00.59.45.png")





You are now ready to take off!!


