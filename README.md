## BSC Year 12 Python Programming Course
For Band 1 Qualification Section of Sixth Form Award at BSC.

## Content
1. Week 1 = Data types, input, output, mathematical operations, string concatenation, functions/subroutines with returns
2. Week 2 = Conditional statements, relational and logical operators, for and while loops, combining control structures.
3. Week 3 = Using modules (math, time, random)
4. Week 4 = Data structures - lists, dictionaries and tuples; returning multiple values from a functions; validation and error handling
5. Week 5 = Continuation of Week 4 
6. Week 6 = Reading/Writing from files - txt and csv ; handling exceptions
7. Week 7 = Using Object-Oriented Programming (OOP) and databases (done over several weeks)

### Example Code
##### Student Score Entry (Week 5)
```py
def gradeValidate():
    while True:
        try:
        score = float(input("Please enter your score from that test: "))
        if score >= 0 and score <= 100:
            return score
        else:
            print('Your test score must be within the range of 0-100.')
    except ValueError:
        print("Invalid input. Please enter a valid number.")

def grade_input():
    subject = input('input the subject of the test: ')
    score = gradeValidate()
    return subject,score

def test_scores():
    scores.append((grade_input()))
    cont = input('continue adding scores? enter "yes" to continue; anything else to exit: ')
    if cont == 'yes':
        test_scores()
    else:
        gradePeek()

def gradePeek():
    num=1
    grade_check = input('check your score? enter "yes" to check; anything else to exit: ')
    if grade_check == 'yes':
        for subject,score in scores:
            print(f'{num}. {subject} test: score: {score}%')
            num+=1
    else:
        raise SystemExit

test_scores()
```
##### Task Manager with File Storage (Week 6)
```py
def validateChoice():
    while True:
        try:
            userChoice = int(input('Choose an option from menu: '))
            if userChoice in range(1,5):
                return userChoice
            else:
                print("enter '1' to add tasks, '2' to check your tasks, '3' to check off tasks or '4' if you wish to quit.")
        except ValueError:
            print("only enter '1', '2', '3' or '4' please!")

def iterValidate():
    while True:
        try:
            iterate = int(input('\nEnter how many tasks you wish to add: '))
            return iterate
        except ValueError:
            print("enter whole numbers please!")   

def numValidate():
    while True:
        try:
            num = int(input('\nEnter the task number you wish to mark as complete: '))
            return num
        except ValueError:
            print("enter whole numbers please!")   

def taskAdd():
    plan_add = input("~~~\nwould you like to add tasks? \ntype 'yes' for yes, anything else for no: ")
    if plan_add == 'yes':
        iterate = iterValidate()
        for i in range(iterate):
            subject = input('\nPlease enter a task: ')
            with open('tasks.txt', 'a') as file:
                print(f'{i+1}. {subject}', file=file)
    print('.\n.\n.')
    return task_manager()

def taskCheck():
    plan_check = input("~~~\nwould you like to check your tasks? \ntype 'yes' for yes, anything else for no: ")
    if plan_check == 'yes':
        with open('tasks.txt', 'r') as file:
            print(file.read())
    print('.\n.\n.')
    return task_manager()

def taskComplete():
    task_comp = input("~~~\nwould you like to mark task as complete? \ntype 'yes' for yes, anything else for no: ")
    if task_comp == 'yes':
        num = numValidate()
        with open('tasks.txt', 'a') as file:
            line_count = 0
            for line in file:
                line_count += 1
                if line_count == num:
                    file.write(f' COMPLETED.')
    print('.\n.\n.')
    return task_manager()

def taskMenu():
    title = "Task Manafer"
    deco ="-"
    menuItems = '''1. Add Tasks
2. Check Tasks
3. Mark Task as Complete
4. Exit Program'''
    print(f"{title}\n{deco*len(title)}\n{menuItems}\n{deco*len(title)}")

def task_manager():
    while True:
        taskMenu()
        userChoice = validateChoice()
        if userChoice == 1:
            print(taskAdd())
        elif userChoice ==2:
            print(taskCheck())
        elif userChoice ==3:
            print(taskComplete())
        else:
            print('exiting...')
        break
```
