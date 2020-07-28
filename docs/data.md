In this section, we'll dig deeper into the fundamentals of working with data by concentrating on data structures and methods for cleaning messy data.  

[TOC]

## What is data again? 
In the last section, we got as far as defining data as "a value assigned to a thing." While that remains true, let's dig a little deeper. If we put on our humanities hat, we start to see data little more complexly. 

In her article, "[Humanities Approaches to Graphical Display](http://www.digitalhumanities.org/dhq/vol/5/1/000091/000091.html)," Johanna Drucker posits the following about data:

> "To overturn the assumptions that structure conventions acquired from other domains requires that we re-examine the intellectual foundations of digital humanities, putting techniques of graphical display on a foundation that is humanistic at its base. This requires first and foremost that we reconceive all data as capta. Differences in the etymological roots of the terms data and capta make the distinction between constructivist and realist approaches clear. Capta is “taken” actively while data is assumed to be a “given” able to be recorded and observed. From this distinction, a world of differences arises. Humanistic inquiry acknowledges the situated, partial, and constitutive character of knowledge production, the recognition that knowledge is constructed, taken, not simply given as a natural representation of pre-existing fact."

This is a long quote, but the concept of "capta" is a useful one. Even if we don't go around calling everything "capta" instead of "data," it is a helpful reminder that data is constructed, especially but not only in the humanities. 

Every single piece of data represents a decision that someone made. The number of rows and columns, the labels, the format, the extent or granularity of the values and the things - these are all choices. They are choices you should consider when creating a data set from scratch or when you use someone else's data. In the rest of this section, we will dig into the details of putting together a data set. 

## Data structures
Data can exist in many different forms. You might imagine a "spreadshet" when thinking about data, but in truth, there are a number of other ways to express and structure your data. 

### Tabular data 
This is our common spreadsheet data structure. Data fits into a table, in which each row represents a thing. Each column is a different field or modifier of that thing. The values reside in each individual cell. In the following table, each row represents one pet. 

|PetID|Name|Animal|Breed|
|---|---|---|---|
|Pet1|Huxley|Cat|Tabby|
|Pet2|Harper|Dog|Flat Coat Retriever|
|Pet3|Hobbes|Dog|Hound|


If you're new to making spreadsheets, it can be tempting to swamp the rows and columns so that each column represents a thing. It can also be tempting to include empty cells as spaces or use visual cues like color or bold/italics to set apart text. These methods will certainly help you as a human, but it's important to keep in mind that most of the software that might process your data will not be able to understand these visual cues. 

Most of the software that will process your data, whether it's for visualization or analysis, will want to see your data in a format known as **CSV** or Comma Separated Value. This format strips away any visual formatting and stores each cell in plain text, separated by a comma. So the above table about pets, would look like this: 

```
PetID,Name,Animal,Breed,
Pet1,Huxley,Cat,Tabby,
Pet2,Harper,Dog,Flat Coat Retriever,
Pet3,Hobbes,Dog,Hound
```

The CSV format reduces file size, simplifies the content, and keeps the file from being dependent on proprietary software like Excel. Fortunately, you don't have to construct your data with commas. Applications like Excel or Google Sheets will let you save or export your file with the file extension `.csv`. It's a good habit to get into when working with data. 


### Relational data 
For some projects, a single table quickly becomes insufficient. Perhaps your project requires collecting data about a group of people, the houses they live in, the land they occupy, etc. It might be time to look into using a database to store all that data. A database works on a relational model - you might have multiple tables, but they are connected through shared values or "keys." Using a database allows you to gather data about many different things, things that may require different fields to describe them. So my table of people may contain a column to note which house they live in, but I can rely on a totally separate table to list all the details about the house itself. This keeps me from cluttering my people table with information that isn't relevant to the main thing my row is about. Often, this is done with an ID number rather than the full title. 

A second advantage of a database is the ability to ask questions of your data. To continue the example from above, I can now ask questions like: How many people live in houses that are yellow? Of the houses on this block, which ones are occupied by people with children? These questions require that I filter based on certain values within each distinct data table and combine them into a new set. Typically, questions like this are asked with a language called **SQL** or Structure Query Language (yes, another language with its own syntax!). 

The basic syntax of SQL looks like this: 

```
SELECT column_name,column_name
FROM table_name
WHERE column_name operator value;
```

And a more specific example might look like this. In this example, the asterisk means everything, so I'm asking for all fields about the cats. 

```
SELECT * FROM pets
WHERE animal='cat';
```

Asking these types of questions of data is often what humanities scholars are after when they decide to build a database. However, designing a database and the interface that goes along with it is a huge endeavor, and often requires the help of a professional database designer. Databases can be built in many different types of software (you might encounter names like MySQL or PostgreSQL), but web-based databases will need to be installed on a server, not just your own computer. If you're undertaking a big project, it's important to assess your resources for creating a database. Fortunately, there are an increasing number of options for storing, visualizing, and analyzing data without database software. Creating well-structured data ensures that your data can be imported into these tools with ease.

### Data serialization
Data serialization is the process by which taken is transformed into another format that can be transferred or stored, then reconstituted. Often, this is necessary so that a programming language or software application can more easily and quickly do something with the data. With serialization comes a few different types of data structures that are important to know. 

**JSON**, or JavaScript Objection Notation, is a way to structure data based on attribute-value pairs and curly brackets. Just like CSV, if you're working with a JSON file, it will have the file extension `.json`. You probably won't end up writing JSON from scratch, but you might have to convert your data to JSON for a certain application. And FYI, JSON is not only used with JavaScript. 

Here's an example. Notice the level of structure introduced with the Address line. There are four fields and values (you might see this called an array) that modify one field, Address. 

```
{
  "PetID": "Pet1",
  "Name": "Huxley",
  "Animal": true,
  "Breed": "Tabby",
  "Address": {
    "streetAddress": "555 5th St.",
    "city": "The Couch",
    "state": "Living Room",
    "postalCode": "55555"
  },
}
```

**XML** or Extensible Markup Language is more than just a serialized data format, it's also a markup language (like HTML). XML has been around a long time, so you will see it referenced in many Digital Humanities projects. XML is highly structured, but allows the user to define the tags that are used. A common application in humanities projects is the [Text Encoding Initiative](https://tei-c.org/) or TEI. TEI is used to markup humanities texts, just like you would markup a website, but instead you use tags like `<l>` for line and `<epigraph>` for epigraph. TEI allows you to do things like build a [website](http://prosody.lib.virginia.edu/) for testing your ability to read rhyme and meter in poetry. It is a foundational practice in DH - the process by which a human interprets a text and encodes the meaning in a way that the computer can understand.

Example: 
```
<lg rhyme="ABCCBBA">
 <l>The sunlight on the <rhyme label="A">garden</rhyme>
 </l>
 <l>
  <rhyme label="A">Harden</rhyme>s and grows <rhyme label="B">cold</rhyme>,</l>
 <l>We cannot cage the <rhyme label="C">minute</rhyme>
 </l>
 <l>Wi<rhyme label="C">thin it</rhyme>s nets of <rhyme label="B">gold</rhyme>
 </l>
 <l>When all is <rhyme label="B">told</rhyme>
 </l>
 <l>We cannot beg for <rhyme label="A">pardon</rhyme>.</l>
</lg>
```


### Textual data 
Not all data has needs to exist in a spreadsheet. In the humanities, we read a lot! We need a way to store textual data, such as a whole book, set of documents, or a century of newspaper articles. A later section will cover the ins and outs of text analysis, but if you're looking to analyze a corpus (another word for collection of texts) of some kind, you need to structure it in some way. 

The common method for storing textual data is in a plain text format or with the file extension `.txt`. Plain text files are just that - documents without the formatting that comes from MS Word or other word processing applications. Just like our HTML documents or our CSV files, a text document simplifies the content for the computer. When we're [counting the number of times Jane Austen used the word "honor"](https://voyant-tools.org/?corpus=austen) or looking for the [use of the word "evolution" over time](https://books.google.com/ngrams/graph?corpus=26&content=evolution%2C+religion&smoothing=3&year_start=1800&year_end=2019&direct_url=t1%3B%2Cevolution%3B%2Cc0%3B.t1%3B%2Creligion%3B%2Cc0), we are concerned with the words in the text, not the way the text looks. Plain text format reduces file size to improve processing time and transfer of data. You'll probably want to use a text editor for viewing these files, just like we did when writing HTML. 

Depending on what you're doing, you will also want to pay attention to the name and organization of your text files. If you noticed in the Voyant instance with Jane Austen, the title of each text was preceded by the year of publication. This file naming strategy makes it easy to sort the texts by their publication date. It's just something to pay attention to when constructing your corpus. 

If you do care about what the text looks like, you might want to look for ways to analyze TEI documents, not just plain text. Text Encoding allows you to add details about the appearance of the text, perhaps there's another hand writing in the margins or use of italics or white space in poetry. 

## Data types 
Once you have settled on the right structure for your data, you need to consider the data types you will use in each field. Most programming languages accept the following:

|Data Type|Example|
|---|---|
|Strings or characters, often surrounded by quote marks| "String!"|
|Integer|4|
|Decimal|4.10|
|Boolean, another way to say true/false or yes/no|TRUE|
|Date, usually formatted as YYYY-MM-DD | 2019-10-20|
|Time, usually formatted as HH:MM:SS | 10:17:26|

There are a few others data types, but these will be most relevant in humanities projects. You will find that Excel loves to chew up and spit out dates unless you standardize formatting in this way. 

## Clean, tidy, and normal data 
As you start to work with data, you'll likely encounter these terms "clean, tidy, normal," used as adjectives and verbs. What do they all mean? How do you know when your data is clean and tidy? Maybe your data is just the black sheep of the family! 

* Cleaning data usually refers to the process of correcting the contents of your dataset. Typos, mistakes, new information can all be cleaned up after the data entry process is complete. You don't have to read every cell one by one, there are a number of tools and methods. Often, visualization your data is a great way to find issues you didn't know you had.

* Tidy data comes from the community around R, the programming language. Tidy data is well-structured, or as [Hadley Wickham](https://vita.had.co.nz/papers/tidy-data.pdf) puts it, "Tidy datasets are easy to manipulate, model and visualise, and have a specific structure: each variable is a column, each observation is a row, and each type of observational unit is a table." Sounds familiar, right?

* Normalized data is a database term. It refers to the process of structuring your tables to reduce redundancy and complexity. Normalized data should be easier for both humans and computers to understand. 

Before we get to tools and methods for straightening up your data, let's take a moment for a pep talk. Data is messy! Whether you created it yourself or are using someone else's data, chances are, something will be wrong with it! The data entry process can be long, and it's easy to change your habits or come upon a better way to record things. This is normal. 

To set yourself up for success, document your decisions as you make them. It is easy to absorbed in your work, make a decision, then put your work down and forget about the decision a week later. Keeping a log of changes will also help anyone else who might be contributing. 

Be consistent! If you want to change a "T" to "True," it's easy to find and replace. It's not as easy to go through a mix of values. 

Finally, remember what the computer is for. It can be tempting to embark on a cleanup project by hand, instead of looking for automated ways to correct your data. Knowing when to cleanup by hand or when to spend the time figuring out how to automate a task is a mark of experience. You won't get it right every time. But it is worthwhile to consider if something can be done in an automated way. Find and replace, when coupled with regular expressions, can be pretty powerful. It can feel like a waste to spend time automating a task when you could just do it, but the skills you learn in the process are valuable and can be applied on future tasks. 

### Data cleaning tools and methods

#### Open Refine
I try to avoid calling technology magic, but [Open Refine](https://openrefine.org/) is magic. It takes some getting used to, but it is indeed a "powerful tool for working with messy data." When you install and run Open Refine, it launches a local server on computer so you interact with the application in your browser. However, just because it's in your browser does not mean it's connected to the internet. Once you've loaded your data, you use the drop down arrows to access various tools for modifying your data. This is not a tool for scrolling through your data, it's used for targeted approaches to specific issues. 

As an example, you can use the "cluster and edit" feature to find similar cells and standardize their contents. The "text facet" feature shows how many cells share the same value. When you sort by alphabetical order, it is really easy to see if you have entered the same name in two different ways. 

There are a number of tutorials on the [documentation page](https://openrefine.org/documentation.html).

#### Excel
Before you get to specialized tools like Open Refine, you can always use Excel or Google Sheets to check your work. 

* Filter - use the filter feature to assess the contents of a single column. You can easily see if a cell is empty or has an incorrect entry. 
* Data Validation - allows you to control what is entered into a cell. You can identify a list of options or select a specific data type. 
* Formulas - there are plenty of spreadsheet formulas designed to work with strings of text. Use the help pages and a search engine to look for examples. There are multiple methods for splitting columns if you need to separate first and last names, or copy over the first half of a string. 

#### Regular Expressions
Regular expressions are a method for matching patterns in text. It's a set of special characters that when used together in certain contexts helps you find and replace in powerful ways. For example, you could find all the phone numbers in a text by looking for the pattern (###) ###-#### or all forms of "women" by using the pattern "wom.n" to replace the fourth character. 

Regular expressions are awesome, but they can get frustrating quickly. Don't be overwhelmed by the complex patterns you encounter in tutorials. Even the basics can come in handy when cleaning data. Plus, there are a lot of resources out there for helping you use them effectively.

* [Regular Expressions 101](https://regex101.com/)
* [Beginning with Regular Expressions](https://recompilermag.com/issues/issue-0/beginning-with-regular-expressions/)
* [Cleaning OCR'd text with regular expressions](https://programminghistorian.org/en/lessons/cleaning-ocrd-text-with-regular-expressions)


## Data modeling 



## Extending your data 

Data modeling? 

Extending, vocabs, reconciling RDF 

## Activities

### Activity 1

## Resources 

https://matthewlincoln.net/2020/05/26/tidy-data-for-humanities.html

https://www-jstor-org.ezproxy.wlu.edu/stable/10.5749/j.ctvg251hk.26?seq=1#metadata_info_tab_contents
 10.5749/j.ctvg251hk.26 

 https://port.sas.ac.uk/mod/book/view.php?id=75&chapterid=133