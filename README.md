# Description

crak is a unix utility for **c**ompiling, **r**unning, **a**nd **k**omparing the outputs of multiple .c programs in the same directory.
The intended use of this script is for grading multiple students programs, and should make grading many files as fast as the crack of a whip!

# Installation

1. Download crak onto your system and place it in a directory where you have run permission.

2. cd to where you downloaded the file and execute `chmod +x crak`.

3. Install "kompare", on Linux use `sudo apt install kompare`.

4. Optional, run `kompare`, select "Diff" on the left, and check all of the whitespace options to ignore all possible whitespace.

# Usage

`crak [-fF] input[.in] sample_output[.out] [file(s) ...]`

1. Save all of you .c files in a single directory. You will also need multiple txt files with your test cases, you can use as many .in files as you would like, and a single output_file. **Make sure to remove all whitespace from file names**, you can do this by running `rename 's/\s/_/g' ./*.c`.

All input files will be run through each code file before running any kompare operations. After input all test cases, outputs will be combined into a single file. This single file is what will be kompared to the given sample_output.out file.

**Make sure to actually use the file extensions .in and .out**

_Support for multiple .out files is planned, in the meantime you can combine your own sample_outputs with `cat *.out > sample_output.out`_

2. Run the following command `crak [args] [input] [sample output] [code file(s)]`

I recommend using `*.c` as your files option, as this will run through all of the .c files in your current directory.

3. crak will then create two new files for each given .c file, an executable version of each file as well as a .txt file with each programs
output. All new files will share the name of the original .c file. A kompare window will be brought up after each file is processed
that will kompare the most recently run program with the sample output given.

Note that the next .c file will not be processed until the kompare window is closed, and aborting the script early will prevent all
.c files from being processed.

## Options
**-f**

Check for AStyle formatting. This is done by creating a copy of each given .c file (reformatted as .formatted) and running a diff against the original .c file and the new .formatted file. The diff operation ignores all whitespace differences. If a difference is found the name of the .c file is output, if there is no difference nothing is output. Formatting will be checked for all given files, and is done after all other operations. This is a much more forgiving option than -F.

**-F**

Check for AStyle formatting. This is done by creating a copy of each given .c file (reformatted as .formatted) and running a diff against the original .c file and the new .formatted file. If a difference is found the name of the .c file is output, if there is no difference nothing is output. Formatting will be checked for all given files, and is done after all other operations.
