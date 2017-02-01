# Phase 1 in R

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

