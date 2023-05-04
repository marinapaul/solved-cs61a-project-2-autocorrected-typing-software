Download Link: https://assignmentchef.com/product/solved-cs61a-project-2-autocorrected-typing-software
<br>
In this project, you will write a program that measures typing speed. Additionally, you will implement typing autocorrect, which is a feature that attempts to correct the spelling of a word after a user types it. This project is inspired by <a href="https://play.typeracer.com/">typeracer</a> <a href="https://play.typeracer.com/">(https://play.typeracer.com/)</a><a href="https://play.typeracer.com/">.</a>

When students in the past have tried to implement the functions without thoroughly reading the problem description, they’ve often run into issues. &#x1f631; Read each description thoroughly before starting to code.

<h2>Final Product</h2>

Our sta solution to the project can be interacted with at <a href="https://cats.cs61a.org/">cats.cs61a.org</a> <a href="https://cats.cs61a.org/">(https://cats.cs61a.org)</a>. If you’d like, feel free to try it out now. When you nish the project, you’ll have implemented a signi cant part of this match yourself!

<h2>Download starter les</h2>

You can download all of the project code as a <a href="https://cs61a.org/proj/cats/cats.zip">zip</a> <a href="https://cs61a.org/proj/cats/cats.zip">archive</a> <a href="https://cs61a.org/proj/cats/cats.zip">(cats.zip)</a>. This project includes several les, but your changes will be made only to cats.py . Here are the les included in the archive:

cats.py : The typing test logic. utils.py : Utility functions for interacting with les and strings. ucb.py : Utility functions for CS 61A projects.

<a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">data/sample_paragraphs.txt</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">:</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">A</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">le</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">containing</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">text</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">samples</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">to</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">be</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">typed.</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">These</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">are</a> <a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">scraped</a>

<a href="https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py">(https://github.com/kavigupta/wikivideos/blob/626de521e04ca643751ed85d549faca6ea528b1d/get_corpus.py) </a>Wikipedia articles about various topics.  <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">data/common_words.txt</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">:</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">A</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">le</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">containing</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">common</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">English</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">words</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">in</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">order</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">of</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">frequency</a>

<a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">(https://github.com/</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">rst20hours/google-10000-english/blob/master/google-10000-english-usa-noswears.txt)</a><a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">.</a>

<a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">data/words.txt</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">:</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">A</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">le</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">containing</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">many</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">more</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">English</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">words</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">in</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">order</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">of</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">frequency</a>

<a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">(https://github.com/</a> <a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">rst20hours/google-10000-english/blob/master/google-10000-english-usa-noswears.txt)</a><a href="https://github.com/first20hours/google-10000-english/blob/master/google-10000-english-usa-no-swears.txt">.</a>

cats_gui.py : A web server for the web-based graphical user interface (GUI). gui_files : A directory of les needed for the graphical user interface (GUI).

multiplayer : A directory of les needed to support multiplayer mode. favicons : A directory of icons. images : A directory of images. ok , proj02.ok , tests : Testing les.

<h2>Logistics</h2>

The project is worth 20 points. 17 points are assigned for correctness, 2 points for composition, and 1 point for submitting Phase 1 by the checkpoint deadline.

You will turn in the following les:

cats.py

You do not need to modify or turn in any other les to complete the project. To submit the project, run the following command: python3 ok –submit

You will be able to view your submissions on the <a href="http://ok.cs61a.org/">Ok</a> <a href="http://ok.cs61a.org/">dashboard</a> <a href="http://ok.cs61a.org/">(http://ok.cs61a.org)</a><a href="http://ok.cs61a.org/">.</a>

For the functions that we ask you to complete, there may be some initial code that we provide. If you would rather not use that code, feel free to delete it and start from scratch. You may also add new function de nitions as you see t.

However, please do not modify any other functions. Doing so may result in your code failing our autograder tests. Also, please do not change any function signatures (names, argument order, or number of arguments).

Throughout this project, you should be testing the correctness of your code. It is good practice to test often, so that it is easy to isolate any problems. However, you should not be testing too often, to allow yourself time to think through problems.

We have provided an autograder called ok to help you with testing your code and tracking your progress.

The rst time you run the autograder, you will be asked to log in with your Ok account using your web browser. Please do so. Each time you run ok , it will back up your work and progress on our servers.

The primary purpose of ok is to test your implementations.

We recommend that you submit after you nish each problem. Only your last submission will be graded. It is also useful for us to have more backups of your code in case you run into a submission issue. If you forget to submit, your last backup will be automatically converted to a submission.

If you do not want us to record a backup of your work or information about your progress, you can run python3 ok –local

With this option, no information will be sent to our course servers. If you want to test your code interactively, you can run

python3 ok -q [question number] -i

with the appropriate question number (e.g. 01 ) inserted. This will run the tests for that question until the

rst one you failed, then give you a chance to test the functions you wrote interactively.

You can also use the debugging print feature in OK by writing  print(“DEBUG:”, x)

which will produce an output in your terminal without causing OK tests to fail with extra output.

<h1>Getting Started Videos</h1>

These videos may provide some helpful direction for tackling the coding problems on the project.

<a href="https://youtu.be/playlist?list=PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB">YouTube</a> <a href="https://youtu.be/playlist?list=PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB">link</a> <a href="https://youtu.be/playlist?list=PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB">(https://youtu.be/playlist?list</a><a href="https://youtu.be/playlist?list=PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB">=</a><a href="https://youtu.be/playlist?list=PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB">PLx38hZJ5RLZex7kSQbMeb5nYavbkv4arB)</a>

<h1>Phase 1: Typing</h1>

<h2>Problem 1</h2>

Throughout the project, we will be making changes to functions in cats.py .

Implement choose . This function selects which paragraph the user will type. It takes three parameters:

a list of paragraphs (strings) a select function, which returns True for paragraphs that can be selected a non-negative index k

The choose function returns the k th paragraph for which select returns True . If no such paragraph exists (because k is too large), then choose returns the empty string.

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 01 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 01

<h2>Problem 2</h2>

Implement about , which takes a list of topic words. It returns a function which takes a paragraph and returns a boolean indicating whether that paragraph contains any of the words in topic .

Once we’ve implemented about , we’ll be able to pass the returned function to choose as the select argument, which will be useful as we continue to implement our typing test.

To be able to make this comparison accurately, you will need to ignore case (that is, assume that uppercase and lowercase letters don’t change what word it is) and punctuation in the paragraph. Additionally, only check for exact matches of the words in topic in the paragraph, not substrings. For example, “dogs” is not a match for the word “dog”.

Before writing any code, unlock the tests to verify your understanding of the question.

python3 ok -q 02 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 02

<h2>Problem 3</h2>

Implement accuracy , which takes a typed paragraph and a reference paragraph. It returns the percentage of words in typed that exactly match the corresponding words in reference . Case and punctuation must match as well. “Corresponding” here means that two words must occur at the same indices in typed and reference —the rst words of both must match, the second words of both must match, and so on.

A word in this context is any sequence of characters separated from other words by whitespace, so treat “dog;” as a single word.

If typed is longer than reference , then the extra words in typed that have no corresponding word in reference are all incorrect.

If both typed and reference are empty, then the accuracy is 100.0. If typed is empty but reference is not empty, then the accuracy is zero. If typed is not empty but reference is empty, then the accuracy is zero.

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 03 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 03

<a href="https://cs61a.org/articles/pair-programming"> </a><a href="https://cs61a.org/articles/pair-programming">Pair</a> <a href="https://cs61a.org/articles/pair-programming">programming?</a> <a href="https://cs61a.org/articles/pair-programming">(/articles/pair-programming)</a> Remember to alternate between driver and navigator roles. The driver controls the keyboard; the navigator watches, asks questions, and suggests ideas.

<h2>Problem 4</h2>

Implement wpm , which computes the words per minute, a measure of typing speed, given a string typed and the amount of elapsed time in seconds. Despite its name, words per minute is not based on the number of words typed, but instead the number of groups of 5 characters, so that a typing test is not biased by the length of words. The formula for words per minute is the ratio of the number of characters (including spaces) typed divided by 5 (a typical word length) to the elapsed time in minutes.

For example, the string “I am glad!” contains three words and ten characters (not including the quotation marks). The words per minute calculation uses 2 as the number of words typed (because 10 / 5 = 2). If someone typed this string in 30 seconds (half a minute), their speed would be 4 words per minute.

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 04 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

python3 ok -q 04

Time to test your typing speed! You can use the command line to test your typing speed on paragraphs about a particular topic. For example, the command below will load paragraphs about cats or kittens. See the

run_typing_test function for the implementation if you’re curious (but it is de ned for you). python3 cats.py -t cats kittens

You can try out the web-based graphical user interface (GUI) using the following command. (You may have to use Ctrl+C or Cmd+C on your terminal to quit the GUI after you close the tab in your browser). python3 cats_gui.py

To submit your Phase 1 checkpoint type:

python3 ok –submit

You can submit again once you’ve nished the whole project, and we will score only your latest submission, but please submit at least once before the checkpoint deadline (after nishing at least the Phase 1 questions) to receive credit for the checkpoint.

<a href="https://cs61a.org/articles/pair-programming"> </a><a href="https://cs61a.org/articles/pair-programming">Pair</a> <a href="https://cs61a.org/articles/pair-programming">programming?</a> <a href="https://cs61a.org/articles/pair-programming">(/articles/pair-programming)</a> This would be a good time to switch roles. Switching roles makes sure that you both bene t from the learning experience of being in each role.

<h1>Phase 2: Autocorrect</h1>

In the web-based GUI, there is an autocorrect button, but right now it doesn’t do anything. Let’s implement automatic correction of typos. Whenever the user presses the space bar, if the last word they typed doesn’t match a word in the dictionary but is close to one, then that similar word will be substituted for what they typed.

<h2>Problem 5</h2>

Implement autocorrect , which takes a typed_word , a list of all valid_words , a diff_function , and a limit .

If the typed_word is contained inside the valid_words list, autocorrect returns that word.

Otherwise, autocorrect returns the word from valid_words that has the lowest di erence from the provided typed_word based on the diff_function . However, if the lowest di erence between typed_word and any of

the valid_words is greater than limit , then typed_word is returned instead.

Important: If typed_word is not contained inside valid_words , and multiple strings have the same lowest di erence from typed_word according to the diff_function , autocorrect should return the string that appears rst in valid_words .

A di function takes in three arguments. The rst two arguments are the two strings to be compared (the typed_word and a word from valid_words ), and the third argument is the limit . The output of the di

function, which is a number, represents the amount of di erence between the two strings.

Here is an example of a di function that computes the minimum of 1 + limit and the di erence in length between the two input strings:

&gt;&gt;&gt; def length_diff(w1, w2, limit): …     return min(limit + 1, abs(len(w2) – len(w1)))

&gt;&gt;&gt; length_diff(‘mellow’, ‘cello’, 10)

1

&gt;&gt;&gt; length_diff(‘hippo’, ‘hippopotamus’, 5)

6

Assume that typed_word and all elements of valid_words are lowercase and have no punctuation.

Hint: Try using max or min with the optional key argument. For some examples of using this argument, check out the lecture slides from Wednesday, September 22.

Before writing any code, unlock the tests to verify your understanding of the question.

python3 ok -q 05 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 05

<h2>Problem 6</h2>

Implement feline_flips , which is a di function that takes two strings. It returns the minimum number of characters that must be changed in the start word in order to transform it into the goal word. If the strings are not of equal length, the di erence in lengths is added to the total.

Here are some examples:

&gt;&gt;&gt; big_limit = 10

&gt;&gt;&gt; feline_flips(“nice”, “rice”, big_limit)    # Substitute: n -&gt; r

1

&gt;&gt;&gt; feline_flips(“range”, “rungs”, big_limit)  # Substitute: a -&gt; u, e -&gt; s

2 &gt;&gt;&gt; feline_flips(“pill”, “pillage”, big_limit) # Don’t substitute anything, length difference of 3.

3

&gt;&gt;&gt; feline_flips(“roses”, “arose”, big_limit)  # Substitute: r -&gt; a, o -&gt; r, s -&gt; o, e -&gt; s, s -&gt; e

5

&gt;&gt;&gt; feline_flips(“rose”, “hello”, big_limit)   # Substitute: r-&gt;h, o-&gt;e, s-&gt;l, e-&gt;l, length difference of

5

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 06 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

python3 ok -q 06

Try turning on autocorrect in the GUI. Does it help you type faster? Are the corrections accurate? You should notice that inserting a letter or leaving one out near the beginning of a word is not handled well by this di function. Let’s x that!

<h2>Problem 7</h2>

Implement minimum_mewtations , which is a di function that returns the minimum number of edit operations needed to transform the start word into the goal word.

There are three kinds of edit operations, with some examples:

Add a letter to start .

Adding “k” to “itten” gives us “kitten” .

Remove a letter from start .

Removing “s” from “scat” givs us “cat” .

Substitute a letter in start for another.

Substituting “z” with “j” in “zaguar” gives us “jaguar” .

Each edit operation contributes 1 to the di erence between two words.

&gt;&gt;&gt; big_limit = 10 &gt;&gt;&gt; minimum_mewtations(“cats”, “scat”, big_limit)       # cats -&gt; scats -&gt; scat

2 &gt;&gt;&gt; minimum_mewtations(“purng”, “purring”, big_limit)   # purng -&gt; purrng -&gt; purring

2 &gt;&gt;&gt; minimum_mewtations(“ckiteus”, “kittens”, big_limit) # ckiteus -&gt; kiteus -&gt; kitteus -&gt; kittens

3

We have provided a template of an implementation in cats.py .

You may modify the template however you want or delete it entirely.

Before writing any code, unlock the tests to verify your understanding of the question.

python3 ok -q 07 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 07

Try typing again. Are the corrections more accurate? python3 cats_gui.py

<a href="https://cs61a.org/articles/pair-programming"> </a><a href="https://cs61a.org/articles/pair-programming">Pair</a> <a href="https://cs61a.org/articles/pair-programming">programming?</a> <a href="https://cs61a.org/articles/pair-programming">(/articles/pair-programming)</a> Celebrate, take a break, and switch roles!

<h2>(Optional) Extension: nal diff (0pt)</h2>

You may optionally design your own di function called final_diff . Here are some ideas for making even more accurate corrections:

Take into account which additions and deletions are more likely than others. For example, it’s much more likely that you’ll accidentally leave out a letter if it appears twice in a row.

Treat two adjacent letters that have swapped positions as one change, not two.

Try to incorporate common misspellings.

You can also set the limit you’d like your di function to use by changing the value of the variable FINAL_DIFF_LIMIT in cats.py .

You can check your final_diff ‘s success rate by running: python3 score.py

If you don’t know where to start, try copy-pasting your code for feline_flips and minimum_mewtations into

final_diff and scoring them. Looking at the typos they accidentally xed might give you some ideas!

<h1>Phase 3: Multiplayer</h1>

Typing is more fun with friends! You’ll now implement multiplayer functionality, so that when you run cats_gui.py on your computer, it connects to the course server at <a href="https://cats.cs61a.org/">cats.cs61a.org</a> <a href="https://cats.cs61a.org/">(https://cats.cs61a.org)</a> and

looks for someone else to race against.

To race against a friend, 5 di erent programs will be running:

Your GUI, which is a program that handles all the text coloring and display in your web browser.

Your cats_gui.py , which is a web server that communicates with your GUI using the code you wrote in

cats.py .

Your opponent’s cats_gui.py .

Your opponent’s GUI.

The CS 61A multiplayer server, which matches players together and passes messages around.

When you type, your GUI uploads what you have typed to your cats_gui.py server, which computes how much progress you have made and returns a progress update. It also uploads a progress update to the multiplayer server, so that your opponent’s GUI can display it.

Meanwhile, your GUI display is always trying to keep current by asking for progress updates from cats_gui.py , which in turn requests that info from the multiplayer server.

Each player has an id number that is used by the server to track typing progress.

<h2>Problem 8</h2>

Implement report_progress , which is called every time the user nishes typing a word. It takes a list of the words sofar , a list of the words in the prompt , the user’s user_id , and a upload function that is used to upload a progress report to the multiplayer server. There will never be more words in sofar than in prompt .

Your progress is a ratio of the words in the prompt that you have typed correctly, up to the rst incorrect word, divided by the number of prompt words. For example, this example has a progress of 0.25 : report_progress([“Hello”, “ths”, “is”], [“Hello”, “this”, “is”, “wrong”], …)

Your report_progress function should do two things: upload a message to the multiplayer server and return the progress of the player with user_id .

You can upload a message to the multiplayer server by calling the upload function on a two-element dictionary containing the keys ‘id’ and ‘progress’ . You should then return the player’s progress, which is the ratio of words you computed.

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 08 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 08

<h2>Problem 9</h2>

Implement time_per_word , which takes in a list words and times_per_player , a list of lists for each player with timestamps indicating when each player nished typing every individual word in words . It returns a match with the given information.

A match is a data abstraction that has a list of words and times . The times are stored as a list of lists of how long it took each player to type every word in words . Speci cally, times[i][j] indicates how long it took player i to type words[j] .

For example, say words = [‘Hello’, ‘world’] and times = [[5, 1], [4, 2]] , then [5, 1] corresponds to the list of times for player 0, and [4, 2] corresponds to the list of times for player 1. Thus, player 0 took 5 units of time to write the word ‘Hello’ .

Important: Be sure to use the match constructor when returning a match . The tests will check that you are using the data abstraction rather than assuming a particular data format.

Read the de nitions for the match constructor and selectors in cats.py to learn more about how the data abstraction is implemented.

Timestamps are cumulative and always increasing, while the values in times are di erences between consecutive timestamps for each player.

Here’s an example: If times_per_player = [[1, 3, 5], [2, 5, 6]] , the corresponding times attribute of the

match would be [[2,2], [3, 1]] . This is because the di erences in timestamps are (3-1) , (5-3) for the rst player and (5-2) , (6-5) for the second player. The rst value of each list within times_per_player

represents the initial starting time for each player.

Before writing any code, unlock the tests to verify your understanding of the question. python3 ok -q 09 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with: python3 ok -q 09

<a href="https://cs61a.org/articles/pair-programming"> </a><a href="https://cs61a.org/articles/pair-programming">Pair</a> <a href="https://cs61a.org/articles/pair-programming">programming?</a> <a href="https://cs61a.org/articles/pair-programming">(/articles/pair-programming)</a> We suggest switching roles now, if you haven’t recently. Almost done!

<h2>Problem 10</h2>

Implement fastest_words , which returns which words each player typed fastest. This function is called once both players have nished typing. It takes in a match .

Speci cally, the fastest_words function returns a list of lists of words, one list for each player, and within each list the words they typed the fastest (against all the other players). In the case of a tie, consider the earliest player in the list (the smallest player index) to be the one who typed it the fastest.

For example consider the following match with the words ‘Just’, ‘have’, and ‘fun’. Player 0 typed ‘fun’ the fastest (3 seconds), Player 1 typed ‘Just’ the fastest (4 seconds), and they tied on the word ‘have’ (both took 1 second) so we consider to Player 0 to be the fastest, because they are the earliest player in the list.

&gt;&gt;&gt; player_0 = [5, 1, 3]

&gt;&gt;&gt; player_1 = [4, 1, 6]

&gt;&gt;&gt; fastest_words(match([‘Just’, ‘have’, ‘fun’], [player_0, player_1]))

[[‘have’, ‘fun’], [‘Just’]]

The match argument is a match data abstraction, like the one returned in Problem 9. You can access words in the match with the selector word_at , which takes in a match and the word_index (an integer). With word_at you can access the time it took any player to type any word using time .

Important: Be sure to use the match constructor when returning a match . The tests will check that you are using the data abstraction rather than assuming a particular data format.

Make sure your implementation does not mutate the given player input lists. For the example above, calling fastest_words on [player_0, player_1] should not mutate player_0 or player_1 .

B