# BSC Yr12 Python Programming_Course
For Band 1 Qualification Section of Sixth Form Award at BSC.

Contains:
1. Week 1 = Data types, input, output, mathematical operations, string concatenation, functions/subroutines with returns
2. Week 2 = Conditional statements, relational and logical operators, for and while loops, combining control structures.
3. Week 3 = Using modules (math, time, random)
4. Week 4 = Data structures - lists, dictionaries and tuples ; returning multiple values from a functions ; validation and error handling
5. Week 5 = Continuation of Week 4 
6. Week 6 = Reading/Writing from files - txt and csv ; handling exceptions
7. Week 7 = Using Object-Oriented Programming (OOP) and databases (done over several weeks)

'''
"def gradeValidate():\n",
    "    while True:\n",
    "        try:\n",
    "            score = float(input(\"Please enter your score from that test: \"))\n",
    "            if score >= 0 and score <= 100:\n",
    "                return score\n",
    "            else:\n",
    "                print('Your test score must be within the range of 0-100.')\n",
    "        except ValueError:\n",
    "            print(\"Invalid input. Please enter a valid number.\")\n",
    "\n",
    "def grade_input():\n",
    "    subject = input('input the subject of the test: ')\n",
    "    score = gradeValidate()\n",
    "    return subject,score\n",
'''
