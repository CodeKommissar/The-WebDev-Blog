---
title: "Playing with scrolls"
date: "2017-04-22T12:02:13-04:00"
draft: false
weight: 4

---

![Scroll](scroll.jpg)

Now that you know how to run basic commands at the terminal, along with a few shortcuts, we are going to start working with files. Because we are wizards, we are going to be playing with "*scrolls*" instead of just simple text files. Inside these scrolls, we are going to write the recipes of our potions.

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

Just like the echo that you would hear in a cavern, the "echo" command repeats the "string" that you wrote between the quotation marks. A string is just a sequence of characters (like letters, numerals and punctuation marks). Although this command doesn't seem that it does much, now you'll see how it can be useful for our purposes.

Enter this command:

	$ echo "Hello Alchemy!" > Invisibility_Potion.txt

{{% notice note %}}
<span class="underline">LifeProTip</span>: Remember to hit the **"[Tab Key](https://www.google.com/search?q=tab+key&oq=tab+key)"** after writing "Inv", so that you don't have to type all of the characters in the "Invisibility_Potion.txt" string.
{{% /notice %}}

The ">" is what is called the "*redirect operator*". The redirect operator (>), redirects the output from the command on the left side into the file on the right hand side.

But how do we know that it actually worked? I'll show you :)

### 3) Viewing a file

In your terminal, type:

	$ cat Invisibility_Potion.txt

As a response, you should get:

	Hello Alchemy!

The "cat" command stands for "con**cat**enation". Concatenation is the action of joining strings together (i.e., when combining the words "Happy" and "Birthday" to wish someone a "Happy Birthday", you are "concatenating" the two strings together). Altough you can indeed use the "cat" command to concatenate files, in this case we're utilizing an extra feature of this command, that it's to display the contents of a file.

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

Notice that this time we used ">>" instead of just ">". If you use the "cat" command again (remember to use the up arrow shortcut) on "Invisibility_Potion.txt", you should receive:

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

### 6) Renaming and Moving files

Let's say that you don't like the name of the "Invisibility_Potion_Copy.txt" file because it has too many characters, how can we change it?

In your terminal type:

	$ mv Invisibility_Potion_Copy.txt IPC.txt

The "mv" command stands for **"Move"**. In this case, we are moving the "Invisibility_Potion_Copy.txt" file into the same location, but changing it's name in the process. After using the "ls" command, you should see that your current files are:

	IPC.txt Invisibility_Potion.txt

Now, if you wanted to move the "ICP.txt" file into another location, let's say, your Desktop, you could use the "mv" command in this way:

	$ mv ICP.txt ~/Desktop

The tilde "~", is shorthand for your home directory, using it this way you can easily access your Desktop directory from anywhere on your computer. The alternative option would be to write:

	$ mv ICP.txt ../../Desktop/

That would mean to go "up", then "up" again, and then "enter" inside the Desktop directory. But that would be more complicated, and could not work depending on where you created the "The_WebDev_Blog" and "The_Command_Line" directories.

Minimize your windows, and check out your desktop, you should have the "ICP.txt" file somewhere in that mess, open it with a text editor and see it's content.

Back in your terminal, at the "The_Command_Line" directory, use the "ls" command. You should have only one file:

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

1. Right now you should be on your "The_WebDev_Blog" directory, use the **pwd** command to confirm it.
2. Create a new directory called "text_files" using the **mkdir** command and enter it with the **cd** command.
3. Inside of the "text_files" directory create a file named "text.txt" with the **touch** command.
4. Write any text into your "text.txt" file with the **echo** command and the redirect operator (>).
5. Write another line of text into your "text.txt" file with the **echo** command and the append operator (>>).
5. Read the contents of your "text.txt" file using the **cat** command.
6. Rename your "text.txt" file to "t.txt" using the **mv** command.
7. Make one copy of your newly named "t.txt" file using the **cp** command. (You can name your copy file anything that you want :)).
7. Go up by one directory using the "cd .." command, so you'll be located on your "The_WebDev_Blog" directory and use the **rm -r** command to delete your "text_files" directory.

When you've finished all of the exercises; **Congratulations!!** You completed The Command Line section! I hope that you enjoyed it and that you learned a lot :D. In the next page there are most of the materials that I used to create this section.
