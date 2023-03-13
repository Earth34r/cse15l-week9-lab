# CSE 15L Week 9 Lab Report

Delaware Wade

Joe Politz

3/9/2023

---

# Lab 3 Extension - Researching Commands - `less`

When a programmer wants to display file contents to the terminal, there are several different options available. One of these is the `cat` command, which dumps the entire file contents to the screen. With small files, this is the perfect choice. But sometimes, more control is needed, especially for large files. `less` is a helpful tool that can display, scroll through, and control the contents of a given file. Below are some of the most common flags used with `less`, and how they are useful.

## Less -f Flag

Normally `less` is configured to refuse nonstandard files like directories, named pipes, and other similar files. But by using `less -f` , the tool can be used to read the contents of directories and non-regular files. The ‘-f’ in the command is short for ‘—force’

Source: [https://phoenixnap.com/kb/less-command-in-linux](https://phoenixnap.com/kb/less-command-in-linux), `less --help` , and ChatGPT

Example 1:

```bash
~$ less -f path-examples

total 24
drwxr-s---  5 cs15lwi23aso ieng6_cs15lwi23 4096 Feb  7 10:57 ./
drwxr-s--- 13 cs15lwi23aso ieng6_cs15lwi23 4096 Mar 10 15:04 ../
drwxr-s---  8 cs15lwi23aso ieng6_cs15lwi23 4096 Feb  7 10:57 .git/
-rw-r-----  1 cs15lwi23aso ieng6_cs15lwi23  249 Feb  7 10:57 Read.java
-rw-r-----  1 cs15lwi23aso ieng6_cs15lwi23   50 Feb  7 10:57 all-java.sh
drwxr-s---  4 cs15lwi23aso ieng6_cs15lwi23 4096 Feb  7 10:57 quiz-layout/
drwxr-s---  4 cs15lwi23aso ieng6_cs15lwi23 4096 Feb  7 10:57 some-files/
path-examples (END)
```

Here `path-examples` is a directory. The output looks very similar to `ls -la` if it was run on the `path-examples` directory. Once the end of file is reached (which is within one page), pressing ‘q’ is necessary to exit `less`.

How could this example be useful?

- Opening directories with less is useful to quickly assess all information about a directory and can be used in conjunction with `less` searches function, allowing information to be extracted with fewer commands then using `grep` and `ls` together.

Example 2:

```bash
~$ less -f /usr/bin

total 550220
dr-xr-xr-x.   2 root root       77824 Mar 12 10:17 ./
drwxr-xr-x.  14 root root        4096 Sep 13  2021 ../
lrwxrwxrwx.   1 root root          30 Sep 13  2021 ControlPanel -> /etc/alternatives/ControlPanel*
-rwxr-xr-x.   1 root root       15059 Jun  9  2014 GET*
-rwxr-xr-x.   1 root root       15059 Jun  9  2014 HEAD*
lrwxrwxrwx.   1 root root          15 Sep 13  2021 Mail -> ../../bin/mailx*
-rwxr-xr-x.   1 root root       15059 Jun  9  2014 POST*
-rwxr-xr-x    1 root root        8812 Sep 25  2018 R*
-rwxr-xr-x    1 root root       11464 May 31  2019 Rscript*
-rwxr-xr-x    1 root root      132600 Sep 13 03:29 VGAuthService*
-rwxr-xr-x    1 root root     1111176 Jan 13  2022 WebKitWebDriver*
lrwxrwxrwx    1 root root           4 Dec 19 14:44 X -> Xorg*
-rwsr-xr-x    1 root root     2447392 Nov 16 07:23 Xorg*
-rwxr-xr-x.   1 root root     2458240 Nov 16  2020 Xvnc*
-rwxr-xr-x.   1 root root       41488 Nov 16  2020 [*
-rwxr-xr-x.   1 root root      107848 Feb  2  2021 a2p*
-rwxr-xr-x    1 root root       52640 Mar 24  2022 ab*
-rwxr-xr-x.   1 root root       11248 Oct  1  2020 abrt-action-analyze-backtrace*
-rwxr-xr-x.   1 root root       11240 Oct  1  2020 abrt-action-analyze-c*
-rwxr-xr-x.   1 root root        1345 Oct  1  2020 abrt-action-analyze-ccpp-local*
-rwxr-xr-x.   1 root root        6821 Oct  1  2020 abrt-action-analyze-core*
-rwxr-xr-x.   1 root root       11224 Oct  1  2020 abrt-action-analyze-oops*
-rwxr-xr-x.   1 root root       11232 Oct  1  2020 abrt-action-analyze-python*
-rwxr-xr-x.   1 root root        2814 Oct  1  2020 abrt-action-analyze-vmcore*
-rwxr-xr-x.   1 root root        1348 Oct  1  2020 abrt-action-analyze-vulnerability*
-rwxr-xr-x.   1 root root       11264 Oct  1  2020 abrt-action-analyze-xorg*
-rwxr-xr-x.   1 root root        5002 Oct  1  2020 abrt-action-check-oops-for-hw-error*
-rwxr-xr-x.   1 root root       11256 Oct  1  2020 abrt-action-generate-backtrace*
-rwxr-xr-x.   1 root root       11240 Oct  1  2020 abrt-action-generate-core-backtrace*
-rwxr-xr-x.   1 root root        8341 Oct  1  2020 abrt-action-install-debuginfo*
-rwxr-xr-x.   1 root root        3207 Oct  1  2020 abrt-action-list-dsos*
-rwxr-xr-x.   1 root root        8958 Oct  1  2020 abrt-action-notify*
-rwxr-xr-x.   1 root root        3535 Oct  1  2020 abrt-action-perform-ccpp-analysis*
-rwxr-xr-x.   1 root root        1292 Oct  1  2020 abrt-action-save-kernel-data*
-rwxr-xr-x.   1 root root       23712 Oct  1  2020 abrt-action-save-package-data*
-rwxr-xr-x.   1 root root       15400 Oct  1  2020 abrt-action-trim-files*
-rwxr-xr-x.   1 root root       48640 Oct  1  2020 abrt-applet*
-rwxr-xr-x.   1 root root       27952 Oct  1  2020 abrt-cli*
/usr/bin
```

This example shows `less -f` being used on a large directory. There are 550,220 results inside of `/usr/bin`, and less allows the user to look through and quit the output inside of the tool without filling up the terminal screen.

How could this example be useful?

- Viewing the contents of very large directories is incredibly useful with `less -f`, because the normal `ls -l` will quickly fill up the entire terminal window, and require aimless scrolling to find the necessary files. Using `less -f` on the other hand eliminates the need to dump the entire contents of long directories into the console.

## Less -M Flag

The `less -M` flag specifies that `less` should display extremely verbose output, including the filename, the current lines being displayed, and the percentage of lines read in the file.

Source of flag: Asked ChatGPT for common `less` flags, also used `less` man pages.

Example 1:

```bash
~$ less -M /skill-demo1-data/written_2/travel_guides/berlitz1/WhereToFrance.txt

WHERE TO GO
        France is a large country of infinite variety, so a great
        many factors come into play as you decide which parts to visit. Do you
        want to see historic sights and tour museums and art galleries? Is
        weather important? Do you want to lie on beaches or hike in mountains?
        Are there children who need to be entertained? Do you want to do a lot
        of driving or restrict your trip to destinations easy to reach by
        train?
        To make the geography (if not the choice) simpler, we<E2><80><99>ve
        divided the country into just five regions: Paris and its vicinity
        (known to the French as the Ile-de-France); the Northeast (Picardy,
        Champagne-Ardennes, Lorraine, Alsace, Burgundy, and the Jura); the
        Northwest (Normandy, Brittany, and the Loire Valley); the Southeast
        (Savoie, the Rhone Valley, Provence, the C<C3><B4>te d<E2><80><99>Azur, and Corsica); and
        the South<C2><AD>west (Berry-Limousin, P<C3><A9>rigord, the Atlantic Coast, the
        Pyr<C3><A9><C2><AD>n<C3><A9>es, and Languedoc-Roussillon).
        It would be impossible to name every place of interest in a
        guide of this size, so we aim to give you a representative overview of
        the country rather than an encyclopedic listing of <E2><80><9C>must-see<E2><80><9D> sites.
        You will still have plenty to choose from.
        Depending on how much time you have, you may want to combine
        two or three of the regions in order to get a sense of the great
        diversity of French life: Paris and the wine country, the mountains, or
        the Atlantic or Mediterranean coasts.
        The itinerary for a first visit to France is bound to
        include Paris. Ideally, divide your stay <E2><80><94> sightseeing in the capital
        at the beginning, spending a leisurely time at a seaside resort or in a
        sunny village in the hills, then shopping in Paris at the end. A
        relaxing vacation, for example, might combine Paris and the
        Ile-de-France with Normandy and Brittany. And for stark contrasts <E2><80><94> of
        climate, countryside, cuisine, and temperament <E2><80><94> combine the capital
        with Provence or Corsica.
        However, the mix shouldn<E2><80><99>t just be geographic. France<E2><80><99>s
        cathedrals, museums, and palaces deserve your attention, but they<E2><80><99>ll be
skill-demo1-data/written_2/travel_guides/berlitz1/WhereToFrance.txt lines 1-39/3769 1%
```

The example enters the less tool, and instead of the usual colon prompt, the prompt contains useful information like the filepath, current lines displayed (1-39 out of 3769) , and 1% (we are 1% of the way through the file).

How could this example be useful?

- This is mostly useful for larger files, where a normal file inspection tool will fail. `cat` and `vim` to take quick glance at the file won’t be able to display its sheer size, where `less -M` allows a summary of information alongside an inspection of the data all in one handy package.

Example 2:

```bash
$ less -M -N skill-demo1-server/FileServer.java

1 import java.io.File;
      2 import java.io.IOException;
      3 import java.net.URI;
      4 import java.net.URISyntaxException;
      5 import java.nio.file.Files;
      6 import java.nio.file.Path;
      7 import java.nio.file.Paths;
      8 import java.util.ArrayList;
      9 import java.util.List;
     10 import java.util.Collections;
     11
     12 class FileHelpers {
     13     static List<File> getFiles(Path start) throws IOException {
     14         File f = start.toFile();
     15         List<File> result = new ArrayList<>();
     16         if(f.isDirectory()) {
     17             File[] paths = f.listFiles();
     18             for(File subFile: paths) {
     19                 result.addAll(getFiles(subFile.toPath()));
     20             }
     21         }
     22         else {
     23             result.add(start.toFile());
     24         }
     25         return result;
     26     }
     27     static String readFile(File f) throws IOException {
     28         return new String(Files.readAllBytes(f.toPath()));
     29     }
     30     static String repeat(String s, int n) {
     31         String result = "";
     32         for(int i = 0; i < n; i += 1) {
     33           result += s;
     34         }
     35         return result;
     36     }
     37 }
     38
     39 class Handler implements URLHandler {
skill-demo1-server/FileServer.java lines 1-39/112 29%
```

This example displays the contents of `~/skill-demo1-server/FileServer.java`. It uses the -M flag in conjunction with the -N flag (shows line numbers) to provide a clean way to browse the code and find out how long the file is.

How could this example be useful?

- This example is tailored to looking at code examples, and displays the line numbers as well. Finding errors using `less`'s pattern matching search with this example is very helpful.

## less +F Flag

Using `less` with the `+F` option allows for real time monitoring of files! As changes are made to the file, the tool will automatically show edits and changes. When used on unnamed pipes, information that flows through the pipe will be displayed immediately.

Source: [https://phoenixnap.com/kb/less-command-in-linux](https://phoenixnap.com/kb/less-command-in-linux) and ChatGPT

Example 1:

```bash
~$ less +F hello.txt

Hello! Welcome to CSE 15L
Waiting for data... (interrupt to abort)
```

In another terminal window, I ran: `echo 'I hope you pass your skill demo!' >> hello.txt`. Now the `less` screen shows:

```bash
Hello! Welcome to CSE 15L
I hope you pass your skill demo!
Waiting for data... (interrupt to abort)
```

This example shows a file being updated by output redirection, which is immediately reflected in the other terminal window.

How could this example be useful?

- This is incredibly useful for monitoring logs in real time, and performing an action as soon as log files are updated. It can also be used to monitor user activity, and see if any potentially malicious edits are being made to system files.

Example 2: Pausing follow mode

```bash
~$ less +F skill-demo1-data/written_2/travel_guides/berlitz1/IntroLosAngeles.txt

... A lot of lines here ...

Waiting for data... (interrupt to abort)
<Ctrl+c>
skill-demo1-data/written_2/travel_guides/berlitz1/IntroLosAngeles.txt (END)
<Shift+f>
Waiting for data... (interrupt to abort)
```

By pressing ‘Ctrl+c’ to abort the follow mode, we get a line at the bottom: `skill-demo1-data/written_2/travel_guides/berlitz1/IntroLosAngeles.txt (END)` - telling us that we’ve reached the end of the file. We can now press ‘q’ to exit, or press ‘F’ to enter follow mode again. By pressing ‘F’ (Shift + f), we return to follow mode without having to restart less.

How could this example be useful?

- This example is mainly useful if we want to pause listening to perform a pattern search in the file, as detailed below. This might be needed if a log file is being monitored for errors or debugging. Resuming pattern searching is easy using the ‘F’ shortcut.

## Less -p and pattern searching flag

The `less` command has a built-in pattern search, activated by pressing ‘/’ while using the tool. You can also jump straight to the first occurrence of a specified regex pattern by using `less -p`. 

Source: ChatGPT and `less` man pages

Example 1:

```bash
~$ less -p "runway" skill-demo1-data/written_2/travel_guides/berlitz1/IntroLosAngeles.txt

blockbuster movie, attempting to keep up with the freeway<E2><80><99>s
        pedal-to-the-metal drivers, or simply scanning the twinkling evening
        skyline from the heights of the Griffith Observatory. In a town where
        the fast lane is the norm and Hollywood isn<E2><80><99>t a place but a state of
        being, you can<E2><80><99>t help feeling part of something exciting and
        unpredictable.
        Much of this energy can be attributed to the residents
        themselves. Nowhere on earth is there a place that attracts such a
        diverse population. The fertile basin edged by mountains and sea and
        blessed with year-round sunshine attracts all kinds with its ideal
        combination of urban and beach living. Then there<E2><80><99>s the enormous
        international community surrounding the entertainment industry. You<E2><80><99>ll
        also discover L.A.<E2><80><99>s large groups of Americans of Chinese, African,
        Korean, Middle Eastern, and Japanese descent. Hispanic Americans
        comprise the largest ethnic group of all, with numbers fast approaching
        40 percent of the population.
        With so many people packed into such a condensed area,
        Angelenos are constantly struggling to create unique identities for
        themselves, which would be more of a challenge if the town didn<E2><80><99>t have
        such an <E2><80><9C>anything goes<E2><80><9D> attitude. The results are often amusing, if not
        outrageous, and can be seen in everything from clothing styles and
        choice of car to how Angelenos spend their time and money.
        No matter what they expect to see in Los Angeles, visitors
        invariably discover sites and experiences that surprise, amuse, shock,
        or excite them. And isn<E2><80><99>t that the reason to come here?
        With the region<E2><80><99>s size and never-ending maze of freeways,
        it<E2><80><99>s no surprise that the car is king in L.A. You must join the masses
        traveling the streets and freeways to get the feel of the place. Leave
        it to Angelenos to make driving an experience in itself. Here, you are
        what you drive, which explains the number of expensive cars beside you
        on the road. You will also notice that people don<E2><80><99>t let traffic time
        stop their productivity<E2><80><82><E2><80><94><E2><80><82>many drivers have their cellular phone
        attached to their ear.
        Finding your way from one place to another is a major part
        of being here; there are attractions scattered from Malibu to
        Disneyland. Fortunately, much of what you<E2><80><99>ll want to see is accessible
        through your car window, because you<E2><80><99>ll likely be spending a lot of
        time driving from one site to another.
        The nation<E2><80><99>s ten busiest freeways are all in the L.A.
:
```

The -p option here jumps straight to the first occurrence of the word ‘freeway’ and highlights it. All occurrences are highlighted, and pressing ‘n’ can jump to the next occurrence of the search.

How can this example be useful?

- Inspecting and searching a file at the same time can be difficult, but `less -p` handles it perfectly. This might be useful if a certain pattern needs to be located from a log file, with additional context read by the programmer as well.

Example 2: Using ‘/’ while `less` is active

```bash
~$ less -M skill-demo1-data/written_2/non-fiction/OUP/Fletcher/ch2.txt
With his carefully crafted two-minute speech at Gettysburg, the best political address in the nation<E2><80><99>s history, Lincoln created a Nomos, a world of norms and meaning, for comprehending the mass slaughter on American soil. The new understanding of why we were in mourning pointed to a resolution of the conflict and the beginnings of a new constitutional order. Rereading the speech now as the preamble to that new order, we can begin to understand the significance of the phrases so carefully chosen. The words of the Gettysburg Address are too powerful, they represent too much concentrated energy and wisdom, to be absorbed in the two minutes that it takes to read them slowly. I suggest that we proceed and listen, sentence by sentence, phrase by phrase, to these words heard so often.
The first sentence states the heart of the matter and sums up the past, present, and future of the American commitment. Four score and seven years ago our fathers brought forth on this continent a new nation, conceived in liberty and dedicated to the proposition that all men are created equal. This sentence alone was enough to formulate the preamble to the new constitution. It harbingers the themes that follow in the address and that will come to dominate American life for the rest of the 1860s. Let us read each of these phrases as elements in the preamble to the postbellum constitutional order.
Four score and seven years ago. . . By 1863, a historical consciousness had taken hold in American thinking. Rooting ourselves in the past stands in sharp contrast to the preamble of the 1787 Constitution, which begins simply, without setting the context: <E2><80><9C>We the people of the United States, in order to form a more perfect Union. . . .<E2><80><9D> There is no reference in the 1787 document to the first settlement dating back some 160 years, no sense that the new country was the outgrowth of an English-speaking culture across the seas. In 1863 the nation still desired to create <E2><80><9C>a more perfect Union,<E2><80><9D> but it had in addition a past that both inspired and troubled the newly indigenous psyche.
The particular past that Lincoln cultivates retains its ability to surprise and to make us take notice. One would expect the president to root his address in the Constitution that created his office, but the great address is defiantly silent about the initial Constitution. As the 1787 document was silent about its great embarrassment, slavery, Lincoln passes over a national charter that carried within it the seeds of war. In this preamble for a new order, the original Constitution is nowhere mentioned. Lincoln locates the birth of the nation four score and seven (eighty-seven) years prior to 1863. Until you do the arithmetic, you do not realize that, in Lincoln<E2>
<80><99>s mind, the critical moment of the founding was 1776, the signing of the Declaration of Independence. For those who knew Lincoln well, this might not have been a surprise, for he had said two years before: <E2><80><9C>I never had a feeling politically that did not spring from the sentiments embodied in the Declaration of Independence.<E2><80><9D>1
The historical retreat to the Declaration of Independence left Lincoln with a major paradox. He claims to be speaking as president, and his office owed its existence to Article II of the Constitution of 1787. Yet, he thought himself back prior to the Philadelphia convention and the creation of the presidency. He pulled the rug of legitimacy out from under his own office. To be able to advocate the principle that all men are created equal, that a nation was born committed to this principle, he had to speak from a time prior to the creation of the government for which the Union troops died.
The precursor to this unusual mode of dating comes in an unexpected place<E2><80><94>in the final paragraph of the Emancipation Proclamation, which went into effect on January 1, 1863:
Done at the City of Washington, this first day of
January, in the year of our Lord one thousand eight
hundred and sixty three, and of the Independence of the
United States of America the eighty-seventh.
By the President: ABRAHAM LINCOLN

It did not occur to Lincoln that there might be some dissonance between his relying on 1776 as the beginning of the American nation and
skill-demo1-data/written_2/non-fiction/OUP/Fletcher/ch2.txt lines 5-17/128 8%
</Lincoln>
```

This example shows using /pattern to jump to the first occurrence of the word ‘Lincoln’ in the file.

How could this example be useful?

- In the case of code or text data like this, being able to scroll while searching is helpful to a user without accidentally editing the text, as would be the case if using `vim` for the same purpose. Using / to quickly search for a pattern in a file is also helpful if the output is being monitored and the developer doesn’t want to exit `less` and rerun the command with the `-p` option.

## Conclusion

Less is an invaluable tool for a linux user, and allows for inspecting files with ease, searching and pattern matching all in one. Using less and learning the above flags can make user workflow cleaner and more efficient.