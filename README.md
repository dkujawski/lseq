# lseq
this was a programming test that I got for a job that I applied for back in 2007

The Problem:
------------

A directory might contain hundreds or even thousands of image
files. Doing an "ls" in this directory will produce a difficult to handle
listing of all these files.

For example, here is an ls of a small directory.

> ls
elem.info         sd_fx29.0112.rgb  sd_fx29.0125.rgb  sd_fx29.0137.rgb
sd_fx29.0101.rgb  sd_fx29.0113.rgb  sd_fx29.0126.rgb  sd_fx29.0138.rgb
sd_fx29.0102.rgb  sd_fx29.0114.rgb  sd_fx29.0127.rgb  sd_fx29.0139.rgb
sd_fx29.0103.rgb  sd_fx29.0115.rgb  sd_fx29.0128.rgb  sd_fx29.0140.rgb
sd_fx29.0104.rgb  sd_fx29.0116.rgb  sd_fx29.0129.rgb  sd_fx29.0141.rgb
sd_fx29.0105.rgb  sd_fx29.0117.rgb  sd_fx29.0130.rgb  sd_fx29.0142.rgb
sd_fx29.0106.rgb  sd_fx29.0118.rgb  sd_fx29.0131.rgb  sd_fx29.0143.rgb
sd_fx29.0107.rgb  sd_fx29.0119.rgb  sd_fx29.0132.rgb  sd_fx29.0144.rgb
sd_fx29.0108.rgb  sd_fx29.0120.rgb  sd_fx29.0133.rgb  sd_fx29.0145.rgb
sd_fx29.0109.rgb  sd_fx29.0121.rgb  sd_fx29.0134.rgb  sd_fx29.0146.rgb
sd_fx29.0110.rgb  sd_fx29.0123.rgb  sd_fx29.0135.rgb  sd_fx29.0147.rgb
sd_fx29.0111.rgb  sd_fx29.0124.rgb  sd_fx29.0136.rgb  strange.xml

Did you notice that the file sd_fx29.0122.rgb was missing?

What we'd rather have is a listing that looks like this:

> lss
   1 elem.info
  46 sd_fx29.%04d.rgb           101-121 123-147
   1 strange.xml

It requires a bit of familiarity with C style printf formatting on the user's
part, but once they get used to it, it's great!

The Assignment:
---------------

Using a language that you are comfortable with (we like C++, Perl or Python
but you can use any mainstream language), write the "lss" command. It accepts
one optional argument: a path to the directory or file, similar to the "ls"
command.

Write it as general as possible. The goal is to find sequences of files that
can be concatenated together. Please don't rely on specific characters as
delimiters since we can't control how artists name their files. And don't
assume anything about the zero-padding.

Beware, we will try your command on some tricky directories, like:

alpha.txt
file01_0040.rgb
file01_0041.rgb
file01_0042.rgb
file01_0043.rgb
file02_0044.rgb
file02_0045.rgb
file02_0046.rgb
file02_0047.rgb
file1.03.rgb
file2.03.rgb
file3.03.rgb
file4.03.rgb
file.info.03.rgb

It should produce:

> lss
   1 alpha.txt
   4 file01_%04d.rgb            40-43
   4 file02_%04d.rgb            44-47
   3 file%d.03.rgb              1-4
   1 file03_info.txt

We encourage the use of existing code to make this assignment easier. Using a
regular expression library, file system calls, interesting data structures and
more are all fair game. (Though if you find an implementation of lss out on
the net, we'd appreciate you not looking at it. That's taking code reuse a
little too far :-) We love the boost library (www.boost.org) and Qt
(www.trolltech.com) though you are not obliged to use either.

We will be examining your code for clarity, correctness, and efficiency. We
are using this to see how you go about solving a problem.

There is no time limit. Though we will wait on the return of this before
proceeding. Please feel comfortable taking at least a week on this.

If anything isn't clear, please feel free to ask questions. That is, after
all, part of the problem solving process.

Enjoy!
