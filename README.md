# <ins> GSoC 2022 Report: Implementing a Very Fast Parser</ins>

<p align="center">
<img src=https://user-images.githubusercontent.com/53227127/130247629-81e83ef8-0d05-4f08-8edf-233abf8a1acb.png width=140 height=140></img>ㅤㅤㅤ<img src=https://user-images.githubusercontent.com/53227127/189484678-1bdc7b1f-f79f-41e0-b4bd-dfbae7caba6f.png height=130></img>
</p>

<h2>About Me</h2>

Hey there! I'm [Akshansh Bhatt](https://www.github.com/akshanshbhatt), a pre-final year (at the time of writing) undergraduate student pursuing a dual major in Physics and Electronics Engineering at [BITS Pilani](https://bits-pilani.ac.in/). I was part of the Google Summer of Code 2022 program as a student developer at [PSF](https://www.python.org/psf/) under the [LPython](https://github.com/lcompilers/lpython/) sub-org. For the past 13 weeks, I, along with my mentors **[Thirumalai Shaktivel](https://github.com/Thirumalai-Shaktivel)** and **[Ondřej Čertík](https://github.com/certik)**, have been working towards building the **LPython compiler**. More specifically, my project involved building the LPython's parser.

You can find the details related to my project [here](https://summerofcode.withgoogle.com/programs/2022/projects/jNVPDsp1). For information related to my weekly progress in the program, you can check out my [blog posts](https://blogs.python-gsoc.org/en/akshanshs-blog). I am available for discussions/feedback on this [email address](mailto:qaz.akshansh@gmail.com). This is my second project (in a row) in Google Summer of Code. In 2021, I had a project under [SymPy](https://github.com/sympy/sympy), details of which you can find on [this link](https://summerofcode.withgoogle.com/projects/6135134387961856).

<h2>Project Synopsis</h2>

My project broadly proposed to accomplish the following goals-

- Write a fully functional Python parser using the Bison Parser Generator that could generate Abstract Syntax Tree (AST) for every valid Python code.
- Test the parser's robustness by comparing the AST generated by the new parser against the ones generated by the CPython's parser on large codebases.
- Benchmark and profile the parser's performance on typically complex cases and report critical slowdowns (if any).

<h2>Work Accomplished</h2>

#### PRs Merged

- [PR #1078](https://github.com/lcompilers/lpython/pull/1078) : [Parser] Fix a bug with indentation of blocks
- [PR #1070](https://github.com/lcompilers/lpython/pull/1070) : [Parser] Fix issue with different indentation type within the same file
- [PR #1068](https://github.com/lcompilers/lpython/pull/1068) : [Parser] Fix a bug in tokenizer related to docstring
- [PR #1053](https://github.com/lcompilers/lpython/pull/1053) : [Parser] Recognise `starred_id` as a valid `id_item`
- [PR #1052](https://github.com/lcompilers/lpython/pull/1052) : [Parser] Parse `@=`
- [PR #1050](https://github.com/lcompilers/lpython/pull/1050) : [Parser] Fix a bug with `not in` token
- [PR #995](https://github.com/lcompilers/lpython/pull/995) : [Parser] Recognise tuple subscript
- [PR #994](https://github.com/lcompilers/lpython/pull/994) : [Parser] Recognise lists and tuples in `GenExpr`
- [PR #993](https://github.com/lcompilers/lpython/pull/993) : [Parser] Recognise `ListComprehension` Subscript
- [PR #979](https://github.com/lcompilers/lpython/pull/979) : [Parser] Refactor `TK_TYPE_COMMENT`
- [PR #976](https://github.com/lcompilers/lpython/pull/976) : [Parser] Fix bug with comment in multiline statements
- [PR #951](https://github.com/lcompilers/lpython/pull/951) : [Parser] Add support for unicode identifiers
- [PR #948](https://github.com/lcompilers/lpython/pull/948) : [Parser] Fix bug with non-ASCII characters in the new parser
- [PR #905](https://github.com/lcompilers/lpython/pull/905) : [Parser] Fix bug with parsing `key:value` in separate lines
- [PR #902](https://github.com/lcompilers/lpython/pull/902) : [Parser] Parse lambda expressions
- [PR #899](https://github.com/lcompilers/lpython/pull/899) : [Parser] Parse multiple statements in single line as `body` of `multiline statements`
- [PR #885](https://github.com/lcompilers/lpython/pull/885) : [Parser] Add support for `GeneratorExp` nodes (new parser)
- [PR #850](https://github.com/lcompilers/lpython/pull/850) : [Parser] Properly handle functions with `*` and `/` in the new parser
- [PR #848](https://github.com/lcompilers/lpython/pull/848) : [Parser] Revert `BoolOp` node generation in the new parser
- [PR #847](https://github.com/lcompilers/lpython/pull/847) : [Parser] Add support for parsing strings with all possible `stringprefix`
- [PR #845](https://github.com/lcompilers/lpython/pull/845) : [Parser] Parse `type_comment` in function args
- [PR #830](https://github.com/lcompilers/lpython/pull/830) : [Parser] Add support for parsing nested function calls
- [PR #810](https://github.com/lcompilers/lpython/pull/810) : [Parser] Recognise default values (keywords) in `class-def`
- [PR #809](https://github.com/lcompilers/lpython/pull/809) : [Parser] Add support for parsing tuples in `for-loop`
- [PR #808](https://github.com/lcompilers/lpython/pull/808) : [Parser] Fix issue 803
- [PR #801](https://github.com/lcompilers/lpython/pull/801) : [Parser] Add `type-comment` support in new parser
- [PR #751](https://github.com/lcompilers/lpython/pull/751) : [Parser] Parse indexing operations on attributes
- [PR #734](https://github.com/lcompilers/lpython/pull/734) : [Parser] Parse raw strings
- [PR #724](https://github.com/lcompilers/lpython/pull/724) : [Parser] Parse `type-comments` in `for-loops`
- [PR #709](https://github.com/lcompilers/lpython/pull/709) : [Parser] Parsing support for `in` (Membership Operator)
- [PR #686](https://github.com/lcompilers/lpython/pull/686) : [Parser] Parse list comprehension
- [PR #682](https://github.com/lcompilers/lpython/pull/682) : [Parser] Parse conditional expressions
- [PR #624](https://github.com/lcompilers/lpython/pull/624) : [Parser] Add support for parsing prefixed strings
- [PR #619](https://github.com/lcompilers/lpython/pull/619) : [Parser] Fix issues with comment and indentation
- [PR #578](https://github.com/lcompilers/lpython/pull/578) : [Parser] Rules for `not in`
- [PR #557](https://github.com/lcompilers/lpython/pull/557) : [Parser] Rules for expressions containing `is` and `is not`
- [PR #538](https://github.com/lcompilers/lpython/pull/538) : [Parser] Parsing rules for `...` and `None`
- [PR #406](https://github.com/lcompilers/lpython/pull/406) : [Parser] Implement single line `if` statement
- [PR #400](https://github.com/lcompilers/lpython/pull/400) : [Parser] Implement parsing rules for functions
- [PR #363](https://github.com/lcompilers/lpython/pull/363) : Fix the `dedent` token generation in new tokenizer

#### Issues Closed

- [Issue #974](https://github.com/lcompilers/lpython/issues/974) : Do not allow mixed (spaces &amp; tab) indent
- [Issue #1023](https://github.com/lcompilers/lpython/issues/1023) : Tokenizer error in the string
- [Issue #1027](https://github.com/lcompilers/lpython/issues/1027) : `Starred id` is not recognized in the comprehension
- [Issue #1025](https://github.com/lcompilers/lpython/issues/1025) : `@=` is not handled in the expression
- [Issue #1024](https://github.com/lcompilers/lpython/issues/1024) : `Not` unexpected in the expression
- [Issue #970](https://github.com/lcompilers/lpython/issues/970) : Tuple Subscript is not recognized
- [Issue #968](https://github.com/lcompilers/lpython/issues/968) : List is not recognized in the GeneratorExp
- [Issue #969](https://github.com/lcompilers/lpython/issues/969) : ListComprehension Subscript is not recognized
- [Issue #972](https://github.com/lcompilers/lpython/issues/972) : Type Comment for the Function decorator is not recognized
- [Issue #973](https://github.com/lcompilers/lpython/issues/973) : Comment after the Singleline Multi statement is not recognized
- [Issue #916](https://github.com/lcompilers/lpython/issues/916) : Non-ascii name is not recognized by the old parser
- [Issue #886](https://github.com/lcompilers/lpython/issues/886) : Singleline multi-statements are not recognized
- [Issue #513](https://github.com/lcompilers/lpython/issues/513) : [New] Parse `/` and `*` as a parameter in function definition
- [Issue #791](https://github.com/lcompilers/lpython/issues/791) : [New] Nested Call is not recognized
- [Issue #787](https://github.com/lcompilers/lpython/issues/787) : [New] Default value (Argument assignment) is not recognized in Class statement
- [Issue #779](https://github.com/lcompilers/lpython/issues/779) : [Parser] Tuples are not parsed in the `for-loop` (new parser)
- [Issue #803](https://github.com/lcompilers/lpython/issues/803) : [Parser] Error in parsing function definition (new parser)
- [Issue #509](https://github.com/lcompilers/lpython/issues/509) : [New] Parse Comments after and inside Multiline statements
- [Issue #612](https://github.com/lcompilers/lpython/issues/612) : [Tokenizer] Segfault during tokenization
- [Issue #617](https://github.com/lcompilers/lpython/issues/617) : [Tokenizer] Newline token not returned after comments
- [Issue #485](https://github.com/lcompilers/lpython/issues/485) : TODO: Extract type hints from the comments
- [Issue #511](https://github.com/lcompilers/lpython/issues/511) : [New] Parse IN and IS in the expression
- [Issue #508](https://github.com/lcompilers/lpython/issues/508) : Parse Single line if and for statements
- [Issue #510](https://github.com/lcompilers/lpython/issues/510) : [New] Parse Ellipsis and None
- [Issue #358](https://github.com/lcompilers/lpython/issues/358) : New tokenizer fails when there are multiple indentations

<h2>Work in Progress</h2>

- Reporting any new issue related to the parser that crops up while testing large codebases. Till now, we have reported all the issues while parsing all the Python files in SymPy and NumPy's codebases, respectively. Currently, we are testing all the Python files in CPython's codebase and we are planning to test even more popular repositories so that every corner case is reported and fixed ASAP.
- Closing all the issues under the [`Parser`](https://github.com/lcompilers/lpython/issues?q=is%3Aissue+is%3Aopen+label%3AParser) tag.

<h2>Outcome</h2>

The new parser is significantly faster than CPython's native parser. To demostrate this, I parsed the entire codebase of [SymPy](https://github.com/sympy/sympy) using both the new and the old parser, and the results are phenomenal!

I wrote a simple script to parse all the Python files in SymPy's codebase. For simplicity, I have broken it down into 4 separate scripts that can be run independently. I have written instructions in form of comments. You can try it out yourself!

_**Script 1**_

```py
''' Part 1 : List all Python file from the root of sympy '''
import os

with open("testall.txt", "r") as f:
    counter = 1
    for root, dirs, files in os.walk("."):
        for file in files:
            if file.endswith(".py"):
                f.write(os.path.join(root, file))
                f.write("\n")
                counter += 1
print("Total:", counter)
```

_**Script 2**_

```py
''' Part 2 : Test and benchmark all the files with old parser, new parser and AST module. Segregate the results into files '''
import os

BINARY_PATH = "/Users/akshansh/Documents/GitHub/lpython/src/bin/lpython"  # Replace it with your path for LPython's binary.

with open("testall.txt", "r") as f:
    for line in f:
        # Generates the AST of the python file using the OLD PARSER (Comment out the two lines below if you want to benchmark the OLD PARSER)
        os.system(f'''if {BINARY_PATH} --show-ast --no-color {line[:-1]} &> temp ; then echo "{line[:-1]}" >> passed_old.txt; else echo "{line[:-1]}" >> failed_old.txt; fi''')
        # Generates the AST of the python file using the NEW PARSER (Comment out the other two lines if you want to benchmark the NEW PARSER)
        os.system(f'''if {BINARY_PATH} --show-ast --no-color --new-parser {line[:-1]} &> temp ; then echo "{line[:-1]}" >> passed_new.txt; else echo "{line[:-1]}" >> failed_new.txt; fi''')
        # Generates the AST of the python file using the PYTHON AST MODULE (Comment out the other two lines if you want to benchmark CPython's AST MODULE)
        os.system(f'''if python3.11 -m ast {line[:-1]} &> temp ; then echo "{line[:-1]}" >> passed_python.txt; else echo "{line[:-1]}" >> failed_python.txt; fi''')
    os.system('rm temp')
```

_**Script 3**_

```py
''' Part 3 : Find all Common files that run fine on both the old and the new parsers '''
os.system("comm -12 <(sort passed_old.txt) <(sort passed_new.txt) > passed_both.txt")
os.system("comm -12 <(sort failed_old.txt) <(sort failed_new.txt) > failed_both.txt")
os.system("comm -23 <(sort failed_old.txt) <(sort failed_new.txt) > failed_only_old_not_new.txt")
os.system("comm -13 <(sort failed_old.txt) <(sort failed_new.txt) > failed_only_new_not_old.txt")
```

_**Script 4**_

```py
''' Part 4 : Generate diffs and find files which generate same output with both the parsers '''
import os

with open("passed_both.txt", "r") as f:
    for line in f:
        # os.system(f'/Users/akshansh/Documents/GitHub/lpython/src/bin/lpython --show-ast --no-color --show-ast {line[:-1]} > temp')
        os.system(f'''lpdiff {line[:-1]} {line[:-1]
          .replace("/Users/akshansh/Documents/GitHub/sympy/","")
          .replace(".py", "")
          .replace("/", "-")}''')
```

After generating all the files using the first script, I benchmarked all the files using all the three methods available for AST generation in the second script (see the comments) and these were the results (Note that `testall.py` is _**Script 2**_) -

```bash
# For the new Parser
$ time python3.11 testall.py
python3.11 testall.py  24.40s user 3.32s system 95% cpu 29.128 total

# Old Parser  (skipping files such as 687, 698) [With timeout]
$ time python3.11 testall.py
python3.11 testall.py  222.49s user 47.07s system 52% cpu 8:33.97 total

# Python's AST Module
$ time python3.11 testall.py
python3.11 testall.py  39.69s user 8.03s system 95% cpu 50.186 total
```

The new parser parsed the entire codebase in just <ins>**29 seconds!**</ins>. This is an incredible boost in performance. It is more than 17.6 times faster than the old parser and about 2 times faster than the state-of-the-art pegen parser of CPython! To prove that this is not a fluke and that I am not cherrypicking data, you can try this out yourself on any Python codbase and verify the validity. 

<h2>Future Work</h2>

- Porting the new parser (Bison) as the main parser for LPython is one of the top priorities right now. After ironing out the left out bugs a little bit more, we will be confident enough that almost every python code will be parsed as anticipated. We can then make the `--show-ast` command show the AST generated by the new parser and consequently retire the current makeshift parser.
- Generating code from AST (unparsing operation).
- Better and consistent benchmarking metrics and tools for the new parser.

<h2>Conclusion</h2>

I had an amazing experience working as a compiler developer this summer. Honestly, I was a bit worried initially because I have never completed any course related to compilers and generally had notions that the inner workings of any compiler are pretty perplexing. I was a bit skeptical about my potential to complete this project, but I am glad I could finish it as planned and learn the best industry practices along the way. I want to thank the developers at LPython for giving me a chance to work on such a pivotal project, especially my mentors - [Thirumalai Shaktivel](https://github.com/Thirumalai-Shaktivel) and [Ondřej Čertík](https://github.com/certik), for guiding me in every way possible and being available whenever I faced any difficulty.

All this was just the beginning. I plan to contribute even more to LPython in the months to come. LPython's development has been going on in full swing, and day by day, we are taking one step towards the goals set for this compiler. It feels surreal to manifest what we have achieved in such a short duration. I am excited about the future of this project!
