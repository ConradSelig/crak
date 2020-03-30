# Description

crak is a unix utility for **c**ompiling, **r**unning, **a**nd **k**omparing the outputs of multiple .c programs in the same directory.
The inteded use of this script is for grading multiple students programs, and should make grading many files as fast as the crack of a whip!

# Installation

1. Download crak onto your system and place it in a directory where you have run permission.

2. cd to where you downloaded the file and execute `chmod +x crak`.

3. Install "kompare", on Linux use `sudo apt install kompare`.

4. Optional, run `kompare`, select "Diff" on the left, and check all of the whitespace options to ignore all possible whitespace.

# Usage

1. Save all of you .c files in a single directory. You will also need two txt files, an input file and a sample output file. **make
sure to remove all whitespace from file names**, you can do this by running `rename 's/\s/_/g' ./*.c`.

2. Run the following command `crak [input txt] [sample output txt] [file(s)]`

I recommend using `*.c` as your files option, as this will run through all of the .c files in your current directory.

3. crak will then create two new files for each given .c file, an executable version of each file as well as a .txt file with each programs
output. All new files will share the name of the original .c file. A kompare window will be brought up after each file is processed
that will kompare the most recently run program with the sample output given.

Note that the next .c file will not be processed until the kompare window is closed, and aborting the script early will prevent all
.c files from being processed.
