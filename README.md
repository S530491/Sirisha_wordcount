# Sirisha_wordcount

## Links
- [Webpage](https://s530491.github.io/Sirisha_wordcount/ "Sirisha Spark Project Webpage")
- [Source](https://github.com/S530491/Sirisha_wordcount "Sirisha Spark Project Source")

## About Me & Objective
My name is Sirisha Vinukonda and I am a student at Northwest Missouri State University. I am from Narsapur, India. I am currently pursuing my masters in applied computer science. The objective of this assignment is to use Spark to find the most frequent words within the text. I choose "TWO GENTLEMEN OF VERONA", an comedy play written by "William Shakespeare".

## Data
I am using william shakespeare comedy play as my data, i have copied the whole play to a txt file.
- [Two gentlemen of verona](http://shakespeare.mit.edu/two_gentlemen/full.html "Website With Full Text")

## Scala Commands
```Scala
> val inputFile = sc.textFile("C:/44564/Sirisha_wordcount/mydata.txt")
> val topWordCount = inputfile.flatMap(str=>str.split(" ")).
     | filter(!_.isEmpty).
     | map(word=>(word,1)).
     | reduceByKey(_+_).
     | map{case (word, count) => (count, word)}.
     | sortByKey(false)
>topWordCount.take(10).foreach(x=>println(x))
```

## Results
The results i got from the above scala commands are:  

| Count | Word |
|-------|------|
| 537   | I    |
| 362   | to   |
| 350   | the  |
| 290   | a    |
| 253   | my   |
| 248   | and  |
| 218   | you  |
| 216   | of   |
| 209   | that |
| 200   | is   |

The most recieved word is "I" in this whole play it is repeated 537 times. The next most repeated number in this list is "to" with 362 times.

With the data i created this chart:  

![mychart](https://user-images.githubusercontent.com/31740152/48318562-5198fa00-e5c8-11e8-8641-6cf5416ab5f2.png "Data chart")
