---
title: "Playing with scrolls"
date: "2017-04-22T12:02:13-04:00"
draft: false
weight: 3

---

![Scroll](scroll.jpg)

Now that you know how to run basic commands at the terminal, along with a few shortcuts, we are going to start working with files. Because we are wizards, we are going to be playing with "*scrolls*" instead of just simple text files. Inside these scrolls, we are going to write the recipes of potions.

Imagine this; you are in your Wizard's Lair, fiddling around with alchemy ingredients (in this case, all you had left was Luna Moth Wings with Chaurus Eggs), and out of pure luck you made an Invisibility potion. Being a very useful type of potion, you want to record the ingredients that you used and their quantity in a scroll. How would you do that?

### 1) Creating files from scratch

First, we need to create the scroll. Open your terminal. When you have it open, go to the "The_Command_Line" directory that you've created in the [Exercises](http://localhost:1313/the_command_line/first_steps/#exercises) portion of the First Steps page.

When you're inside that directory, enter this command:

	$ touch Invisibility_Potion.txt

The "touch" command simply creates an empty file. In this case we're using the "touch" command to create an empty file named "Invisibility_Potion.txt". If you now enter the "ls" command, you should get the name of the file that you've just created:

	Invisibility_Potion.txt

The original purpose of "touch" was to change the modification time of files or directories (and still does that), but nowadays we mostly use it to create empty files.

### 2) Writing into files

Now that we have an empty file, we need to learn how to write some text into it. For this, we are going to make use of the "echo" command. This command simply writes text into the terminal.

In your terminal, type:

	$ echo "Abracadabra!"

As a response, you should get:

	Abracadabra!

Just like the echo that you would hear in a cavern, the "echo" command repeats the "string" that you wrote between the quotation marks. A string is just a sequence of characters (like letters, numerals and punctuation marks). This command doesn't seem that it does much, but now you'll see how it can be useful for our purposes.

Enter this command:

	$ echo "Hello Alchemy!" > Invisibility_Potion.txt

{{% notice note %}}
Try to use the "Tab" key so that you don't have to type all the characters in "Invisibility_Potion.txt"
{{% /notice %}}

The ">" is what is called the "*redirect operator*". The > redirects the output from the command on the left side into the file on the right hand side.

But how do we know that it actually worked? Let's see how.

### 3) Viewing a file

In your terminal, type:

	$ cat Invisibility_Potion.txt

As a response, you should get:

	Hello Alchemy!

The "cat" command stands for "con**cat**enation". Concatenation is the action of joining strings together (i.e., when combining the words "Happy" and "Birthday" to wish someone a "Happy Birthday", you are "concatenating" the two strings together). Altough you can indeed use the "cat" command to concatenate files, in this case we're utilizing another feature of this command, that it's to display the contents of a file.

### 4) More Writing

That is pretty neat! You wrote text into a file without using a text editor or a word processor, but what if you'd' like to write more than one line in that file?

In your terminal, type:

	$ echo "Ingredients to create an Invisibility Potion:" > Invisibility_Potion.txt

If you use the "cat" command on Invisibility_Potion.txt, as a response, you should receive:

	Ingredients to create an Invisibility Potion:

What happended to the "Hello Alchemy!" that was in the beginning??

<span class="underline">Answer:</span> It was overwritten. Used with the "redirect operator" (>), the "echo" command overwrites the contents of a file.

If we want to add some extra lines of text into the file, we need to use the "append operator" (>>). In your terminal, enter:

	$ echo "* 2 Luna Moth Wings" >> Invisibility_Potion.txt

Notice that this time we used ">>" instead of just ">". If you use the "cat" command again (remember to use the up arrows) on "Invisibility_Potion.txt", you should receive:

	Ingredients to create an Invisibility Potion:
	* 2 Luna Moth Wings

Let's add the other ingredient:

	$ echo "* 3 Chaurus Eggs" >> Invisibility_Potion.txt

If we display the contents of "Invisibility_Potion.txt" again, this would be the result:

	Ingredients to create an Invisibility Potion:
	* 2 Luna Moth Wings
	* 3 Chaurus Eggs

### 5) Copying files

Now, let's say, you want to make a copy of this Invisibility Potion recipe and send it to a friend. This is very achievable by using the "cp" command.

At your terminal type:

	$ cp Invisibility_Potion.txt Invisibility_Potion_Copy.txt

The "cp" command stands for **"Copy"**. If you enter the "ls" command now, it should display two files in your folder:

	Invisibility_Potion_Copy.txt Invisibility_Potion.txt 	

And if you use the "cat" command with "Invisibility_Potion_Copy.txt" as an argument, the text should correspond with the contents of "Invisibility_Potion.txt":

	Ingredients to create an Invisibility Potion:
	* 2 Luna Moth Wings
	* 3 Chaurus Eggs

You succesfully copied a file, but what else we can do with it?

### 6) Renaming Files and Moving files

Let's say that you don't like the name of the "Invisibility_Potion_Copy.txt" file because you feel it is too large, how can we change it?

In your terminal type:

	$ mv Invisibility_Potion_Copy.txt IPC.txt

The "mv" command stands for **"Move"**. In this case, we are moving the "Invisibility_Potion_Copy.txt" file into the same location, but changing it's name in the process. After using the "ls" command, you should see that your current files are:

	IPC.txt Invisibility_Potion.txt

Now, if you wanted to move the "ICP.txt" file into another location, let's say, your Desktop, you could do this:

	$ mv ICP.txt ~/Desktop

The tilde "~", is shorthand for your home directory, using it this way you can easily access your Desktop directory from anywhere on your computer. The alternative would be to write:

	$ mv ICP.txt ../../Desktop/

That would mean to go "up", then "up" again, and then "enter" inside the Desktop directory. But that would be more complicated, and could not work depending on where you created the "The_WebDev_Blog" and "The_Command_Line" directories.

Minimize your windows, and check out your desktop, you should have the "ICP.txt" file somewhere in that mess, open it with a text editor and see it's content.

Back in your terminal, at the "The_Command_Line" directory, use the "ls" command, you should have only one file:

	Invisibility_Potion.txt

All seems fine, but creating scrolls, writing into them, copying their contents and etcetera, leaved you a little paranoid. You are a little afraid that your enemies find this Invisibility Potion Recipe and use it against you. So you decide that you should get rid of this recipe.

### 7) Deleting files

To delete files **permanently**, we use the "rm" command, like this:

	$ rm Invisibility_Potion.txt

The "rm" command stands for **"Remove"** and here we are using it to delete our "Invisibility_Potion.txt" file. If you use the "ls" command, your directory should be empty of files.

{{% notice warning %}}
What can you do if you want to recover your "Invisibility_Potion.txt" file? <br><br>Pretty much nothing (feel lucky that you have a backup in your Desktop haha). The files deleted using the "rm" command are completely removed from your computer. They're not even in the Trash, so be extra careful when using the "rm" command.
{{% /notice %}}

Now that you have zero files, I want you to create a couple of dummy files. I'll do it like this:

	$ touch dummy.txt
	$ touch dummy.py
	$ touch dummy.html

{{% notice note %}}
Notice that using "touch", you can create files with any extension that you want.
{{% /notice %}}

Make use of the "cd" command and go one directory above ("cd .." if you don't remember how). If you use "ls", you should receive only one directory as a response:

	The_Command_Line

Try to delete this directory with the "rm" command:

	$ rm The_Command_Line

It doesn't work... As a response, you should receive something like:

	rm: cannot remove 'The_Command_Line/': Is a directory

It failed because you can't delete a directory with just the "rm" command. To remove a directory, you need to learn what "flags" are.

In your terminal, enter:

	$ rm -r The_Command_Line

If you use the "ls" command, you should see that you have succesfully deleted "The_Command_Line" directory.

The "-r" after the "rm" command is called a "flag" or "option". Flags can change and even enhance commands, and are added using a single dash (-) after the command.

In this case the "-r" flag stands for *recursive* which means that it is going to remove all the contents of the directory [recursively](https://www.google.co.ve/search?q=recursion). Be very careful with this option, it is not unheard of people that deleted all of their system files with this combination.

---

### Quiz

Solve the quiz that correspond this page and then move into the exercises.

{{% button href="http://lrodriguez.me/The_WebDev_Blog_Quizzes/The_Command_Line/Quiz_Number_2/index.html" icon="fa fa-share" icon-position="right" %}}Go to Quiz{{% /button %}}

### Exercises

1. In your *home* directory, create a directory called "The_WebDev_Blog".
2. Enter the "The_WebDev_Blog" directory using the "cd" command.
3. Inside of the "The_WebDev_Blog" directory create a directory called "The_Command_Line".
4. Use the "ls" command to confirm that you have created the "The_Command_Line" directory.
5. Enter the "The_Command_Line" directory
6. Use the "pwd" command to know where are you located
7. Return to your home directory using the "cd .." command (twice)

When you've finished the exercises, go to the next page so you can learn some helpful shortcuts!



















<!--

> Let’s pick up (more or less) where we left off in Section 1, with an echo command to print out the first line of Shakespeare’s first sonnet (Listing 6):

	$ echo "From fairest creatures we desire increase,"
	From fairest creatures we desire increase,

> Our task now is to create a file containing this line. Even without the benefit of a text editor, it is possible to do this using the redirect operator >:

	$ echo "From fairest creatures we desire increase," > sonnet_1.txt

> (Recall that you can use up arrow to retrieve the previous command rather than typing it from scratch.) Here the right angle bracket > takes the string output from echo and redirects its contents to a file called sonnet_1.txt.

> How can we tell if the redirect worked? We’ll learn some more advanced command-line tools for inspecting files in Section 3, but for now we’ll use the cat command, which simply dumps the contents of the file to the screen:

	$ cat sonnet_1.txt
	From fairest creatures we desire increase,

> The name cat is short for “concatenate”, which is a hint that it can be used to combine the contents of multiple files, but the usage above (to dump the contents of a single file to the screen) is extremely common. Think of cat as a “quick-and-dirty” way to view the contents of a particular file (Figure 14).14
cat
Figure 14: Viewing a file with cat.

> In order to add the second line of the sonnet (in modernized spelling), we can use the append operator >> as follows:

	$ echo "That thereby beauty's Rose might never die," >> sonnet_1.txt

> This just adds the line to the end of the given file. As before, we can see the result using cat:

	$ cat sonnet_1.txt
	From fairest creatures we desire increase,
	That thereby beauty's Rose might never die,

> (To get to this command, I hope you just hit up arrow twice instead of retyping it. If so, you’re definitely getting the hang of this.) The result above shows that the double right angle bracket >> appended the string from echo to the file sonnet_1.txt as expected.

> Modernized treatments of the Sonnets sometimes emend Rose to rose (thereby obscuring the likely meaning), and we can make a second file following this convention using two more calls to echo:

	$ echo "From fairest creatures we desire increase," > sonnet_1_lower_case.txt
	$ echo "That thereby beauty's rose might never die," >> sonnet_1_lower_case.txt

> In order to facilitate the comparison of files that are similar but not identical, Unix systems come with the helpful diff command:

	$ diff sonnet_1.txt sonnet_1_lower_case.txt
	< That thereby beauty's Rose might never die,

	> That thereby beauty's rose might never die,

> When discussing computer files, diff is frequently employed both as a noun (“What’s the diff between those files?”) and as a verb (“You should diff the files to see what changed.”). As with many technical terms, this sometimes bleeds over into common usage, such as “Diff present ideas against those of various past cultures, and see what you get.”15

> Perhaps the mostly frequently typed command on the Unix command line is ls, short for “list” (Listing 8).

> Listing 8: Listing files and directories with ls. (Output will vary.)

	$ ls
	Desktop
	Downloads
	sonnet_1.txt
	sonnet_1_reversed.txt

> The ls command simply lists all the files and directories in the current directory (except for those that are hidden, which we’ll learn more about in a moment). In this sense, it’s effectively a command-line version of the graphical browser used to show files and directories (also called “folders”), as seen in Figure 15. (We’ll sharpen our understanding of directories and folders in Section 4.) As with a graphical file browser, the output in Listing 8 is just a sample, and results will differ based on the details of your system. (This goes for all the ls examples, so don’t be concerned if there are minor differences in output.)

> The ls command can be used to check if a file (or directory) exists, because trying to ls a nonexistent file results in an error message, as seen in Listing 9.
Listing 9: Running ls on a nonexistent file.

	$ ls foo
	ls: foo: No such file or directory
	$ touch foo
	$ ls foo
	foo

> Listing 9 uses the touch command to create an empty file with the name foo (Box 7), so the second time we run ls the error message is gone. (The stated purpose of touch is to change the modification time on files or directories, but (ab)using touch to create empty files as in Listing 9 is a common Unix idiom.)

One useful ability of ls is support for the wildcard character * (read “star”). For example, to list all files ending in “.txt”, we would type this:

$ ls *.txt
sonnet_1.txt
sonnet_1_reversed.txt

Here *.txt (read “star dot tee-ex-tee”) automatically expands to all the filenames that match the pattern “any string followed by .txt”.

Finally, Unix has the concept of “hidden files (and directories)”, which don’t show up by default when listing files. Hidden files and directories are identified by starting with a dot ., and are commonly used for things like storing user preferences. For example, in Learn Enough Git to Be Dangerous, we’ll create a file called .gitignore that tells a particular program (Git) to ignore files matching certain patterns. As a concrete example, to ignore all files ending in “.txt”, we could do this:

$ echo "*.txt" > .gitignore
$ cat .gitignore
*.txt

If we then run ls, the file won’t show up, because it’s hidden:

$ ls
sonnet_1.txt
sonnet_1_reversed.txt

To get ls to display hidden files and directories, we need to pass it the -a option (for “all”):

$ ls -a
.           .gitignore      sonnet_1_reversed.txt
..          sonnet_1.txt

Now .gitignore shows up, as expected. (We’ll learn what . and .. refer to in Section 4.3.)

Next to listing files, probably the most common file operations involve renaming, copying, and deleting them. As with listing files, most modern operating systems provide a graphical user interface to such tasks, but in many contexts it is more convenient to perform them at the command line.

The way to rename a file is with the mv command, short for “move”:

$ echo "test text" > test
$ mv test test_file.txt
$ ls
test_file.txt

This renames the file called test to test_file.txt. The final step in the example runs ls to confirm that the file renaming was successful, but system-specific files other than the test file are omitted from the output shown. (The name “move” comes from the general use of mv to move a file to a different directory (Section 4), possibly renaming it en route. When the origin and target directories coincide, such a “move” reduces to a simple renaming.)

The way to copy a file is with cp, short for “copy”:

$ cp test_file.txt second_test.txt
$ ls
second_test.txt
test_file.txt

Finally, the command for deleting a file is rm, for “remove”:

$ rm second_test.txt
remove second_test.txt? y
$ ls second_test.txt
ls: second_test.txt: No such file or directory

Note that, on many systems, by default you will be prompted to confirm the removal of the file. Any answer starting with the letter “y” or “Y” will cause the file to be deleted, and any other answers will prevent the deletion from occurring.

By the way, in the calls to cp and rm above, I would almost certainly not type out test_file.txt or second_test.txt. Instead, I would type something like test⇥ or sec⇥ (where ⇥ represents the tab key (Table 1)), thereby making use of tab completion (Box 8).
Box 8. Tab completion

Most modern command-line programs (shells) support tab completion, which involves automatically completing a word if there’s only one valid match on the system. For example, if the only file starting with the letters “tes” is test_file, we could create the command to remove it as follows:

 $ rm tes⇥

where ⇥ is the tab key (Table 1). The shell would then complete the filename, yielding rm test_file. Especially with longer filenames (or directories), tab completion can save a huge amount of typing. It also lowers the cognitive load, since it means you don’t have to remember the full name of the file—only its first few letters.

If the match is ambiguous, as would happen if we had files called foobarquux and foobazquux, the word will be completed only as far as possible, so

 $ ls foo⇥

would be completed to

 $ ls fooba

If we then hit tab again, we would see a list of matches:

 $ ls fooba⇥
 foobarquux foobazquux

We could then type more letters to resolve the ambiguity, so typing the r after fooba and hitting ⇥ would yield

 $ ls foobar⇥

which would be completed to foobarquux. This situation is common enough that experienced command-line users will often just hit something like f⇥⇥ to get the shell to show all the possibilities:

 $ ls f⇥⇥
 figure_1.png foobarquux  foobazquux

Additional letters would then be typed as usual to resolve the ambiguity.

The default behavior of rm on an unconfigured Unix system is actually to remove the file without confirmation, but (because deletion is irreversible) many systems alias the rm command to use an option to turn on confirmation. (As you can verify by running man rm, this option is -i, so in fact rm is really rm -i.) There are many situations where confirmation is inconvenient, though, such as when you’re deleting a list of files and don’t want to have to confirm each one. This is especially common when using the wildcard * introduced in Section 2.2. For example, to remove all the files ending with “.txt” using a single command, without having to confirm each one, you can type this:

$ rm -f *.txt

Here -f (for “force”) overrides the implicit -i option and removes all files immediately. (N.B. You are now in a position to understand the command in Figure 2.)

EXERCISES

-->
