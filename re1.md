PROJECT REPORT

Project Title
VIT Bhopal SGPA and CGPA Calculator

1. Introduction

This project is a Python-based command-line application developed to calculate SGPA and CGPA using the VIT-style 10-point grading system. The program allows a student to enter academic details such as subject names, credits, grades, semester SGPAs, and semester credits, then automatically computes the final result using weighted average formulas.

The project was built as a practical solution to a very common student problem: calculating grade performance accurately without relying on repeated manual calculations. Although SGPA and CGPA look simple at first glance, they depend on weighted credits, which makes manual computation slow and error-prone. This project turns that process into a simple guided interaction.

2. Problem Statement

Students often need to calculate their SGPA or CGPA to track academic progress, estimate eligibility for scholarships or placements, and understand their overall performance. In many cases, students either calculate this manually or use unreliable online tools that may not match their university's grading pattern.

The specific problem addressed in this project is:

How can we create a simple, reliable, and easy-to-use calculator that helps students compute SGPA and CGPA correctly according to the VIT grading system?

This problem matters because:
- SGPA and CGPA are weighted averages, not simple averages.
- Manual calculation can lead to mistakes, especially when many subjects or semesters are involved.
- Students often want quick results without doing the same arithmetic repeatedly.
- A personalized tool gives better confidence than using an unknown external calculator.

3. Why the Problem Matters

Academic performance indicators such as SGPA and CGPA are important in student life. They are often used in internship applications, higher studies, scholarships, and placement filtering. Even a small error in calculation can create confusion or lead to poor planning.

This project is meaningful because it solves a real and immediate problem faced by students. Instead of focusing only on theory, it applies programming to an everyday educational use case. It also shows how software can reduce human error and improve decision-making in a simple but effective way.

4. Project Objectives

The main objectives of the project were:
- To build a working SGPA and CGPA calculator in Python
- To support the VIT Bhopal 10-point grade system
- To provide more than one way to calculate CGPA
- To prevent invalid input through proper validation
- To keep the program beginner-friendly and easy to use from the terminal
- To write clean and modular code using functions

5. Scope of the Project

The current scope of the project includes:
- SGPA calculation from subject-wise grades and credits
- CGPA calculation from semester SGPAs and semester credits
- CGPA calculation directly from all subject grades across multiple semesters
- Input validation for numbers and grades
- Clear display of totals and final results

The project does not currently include:
- A graphical user interface
- Persistent data storage
- PDF or file export of the result
- Support for multiple university grading systems

6. Approach to Solving the Problem

The solution approach was to design an interactive command-line tool that guides the user step by step and performs the required weighted calculations automatically.

The project was divided into the following logical parts:

First, a grade-to-point mapping was defined using a Python dictionary. This allows letter grades like S, A, B, and C to be converted into numerical values needed for calculation.

Second, separate helper functions were created for input validation. Instead of writing validation logic repeatedly, functions such as `get_positive_int`, `get_positive_float`, `get_float_in_range`, and `get_grade` were used to ensure only valid values are accepted.

Third, the calculator logic was separated into three main functions:
- `calculate_sgpa()`
- `calculate_cgpa_from_semesters()`
- `calculate_cgpa_from_courses()`

This made the program easier to understand, test, and extend.

Finally, a `main()` function was used to display the menu, explain the grading table, and direct the user to the required mode of calculation.

7. System Design and Working

The application follows a simple menu-driven structure. When the program starts, it displays the title and the grade mapping table. It then asks the user to choose one of three options.

Option 1: Calculate SGPA from subject grades
In this mode, the user enters the number of subjects in a semester. For each subject, the program asks for:
- Subject name
- Credits
- Grade

The program multiplies each subject's credit by the corresponding grade point, sums the results, divides by total credits, and displays the SGPA.

Option 2: Calculate CGPA from semester SGPAs
In this mode, the user enters the number of completed semesters. For each semester, the program asks for:
- Semester SGPA
- Semester credits

The program then calculates the weighted average of all semester SGPAs.

Option 3: Calculate CGPA directly from all course grades
In this mode, the user enters the number of semesters and then enters subject-wise details for each semester. This gives a more detailed and direct CGPA calculation from raw academic data.

8. Grade Mapping Used

The program uses the following VIT-style grade mapping:

- S = 10
- A = 9
- B = 8
- C = 7
- D = 6
- E = 5
- F = 0
- N = 0

This mapping is stored in the `GRADE_POINTS` dictionary and is reused throughout the program.

9. Formulas Used

The correctness of the project depends on using weighted average formulas rather than ordinary averages.

SGPA Formula:
SGPA = Sum of (Credits x Grade Points) / Sum of Credits

CGPA from Semester SGPA Formula:
CGPA = Sum of (Semester SGPA x Semester Credits) / Sum of Semester Credits

CGPA from All Course Grades Formula:
CGPA = Sum of (Credits x Grade Points for all subjects) / Sum of Credits for all subjects

Approximate Percentage:
Percentage = CGPA x 10

This percentage is only an estimate and may not exactly match official university conversion rules.

10. Key Design Decisions

Several important decisions were made while building the project.

Decision 1: Use a command-line interface
The project was designed as a terminal-based program instead of a GUI application. This decision kept the project simple, lightweight, and focused on core logic.

Decision 2: Use functions for modularity
Instead of writing everything inside one large block, the program was divided into small reusable functions. This improved readability and made debugging easier.

Decision 3: Include multiple calculation modes
Students do not always have the same type of data available. Some know individual subject grades, while others only know semester SGPAs. Supporting three modes made the tool more flexible.

Decision 4: Add strict input validation
A major focus of the project was preventing invalid data from affecting the result. Repeated input prompts ensure that the program produces meaningful output only from valid inputs.

Decision 5: Use a dictionary for grade mapping
A dictionary is simple, efficient, and easy to update if the grading scheme changes in the future.

Decision 6: Allow decimal credits
Credits are not always whole numbers, so the program accepts floating-point credit values to make the calculator more realistic and practical.

11. Challenges Faced

Although the program is conceptually simple, a few practical challenges came up during development.

Challenge 1: Handling invalid user input
Users can enter letters where numbers are expected, negative values, blank inputs, or unsupported grades. A lot of attention had to be given to validation so the program would not crash or calculate incorrect results.

Challenge 2: Designing clear program flow
Since the project has three different calculation modes, it was important to keep the interaction simple and not confuse the user. The menu and prompts had to be arranged carefully.

Challenge 3: Managing repeated logic
Without proper planning, the same validation or calculation logic could have been repeated in multiple places. This was solved by creating helper functions and separating responsibilities clearly.

Challenge 4: Balancing simplicity and usefulness
The project needed to remain simple enough for a beginner-level Python project, but still useful in a real academic setting. Choosing the right features without overcomplicating the code was an important part of development.

12. How the Challenges Were Solved

The input validation challenge was solved by writing dedicated functions that keep asking the user until a valid value is entered.

The multi-mode workflow challenge was solved by separating each calculator into its own function and keeping `main()` responsible only for navigation.

The code duplication challenge was reduced by reusing the grade dictionary and helper functions across all calculation methods.

The simplicity challenge was handled by keeping the interface text clear, limiting the number of menu options, and avoiding advanced features that were not necessary for the first version.

13. Testing and Verification

The program can be tested by running it with different combinations of valid and invalid input.

Examples of useful test cases include:
- A normal SGPA calculation with 4 or 5 subjects
- A CGPA calculation using semester SGPAs with different credit totals
- A detailed CGPA calculation across multiple semesters
- Entering invalid grades such as `P` or `X`
- Entering negative or zero credits
- Entering non-numeric values for subject count or SGPA

The expected behavior is that:
- Valid values are accepted and used in the calculation
- Invalid values are rejected with a clear message
- The program continues asking until the user provides correct input
- Final SGPA or CGPA is shown in formatted form

14. Learning Outcomes

This project provided several valuable learning outcomes.

Technical learning:
- Understanding how weighted averages work in real applications
- Using dictionaries effectively for data mapping
- Writing reusable functions to reduce duplication
- Applying loops and conditional statements in a menu-driven program
- Validating user input carefully to improve reliability
- Structuring a Python program into logical components

Practical learning:
- Building software around a real user problem
- Thinking about usability, not just correctness
- Designing prompts and output in a way that is easy to follow
- Realizing that small tools can still require careful planning

15. Strengths of the Project

The main strengths of the project are:
- It solves a real student problem
- It is easy to run and understand
- It has clear modular code structure
- It supports multiple academic calculation scenarios
- It reduces manual errors through automated weighted calculations
- It includes strong input validation for a beginner-friendly application

16. Limitations

Like any first version, the project has some limitations:
- It runs only in the terminal
- It does not save user data for future reuse
- It assumes one fixed grading system
- It gives only an approximate percentage conversion
- It does not generate printable reports automatically

These limitations do not reduce the usefulness of the project, but they show areas where the program can be improved.

17. Future Enhancements

The project can be expanded in several ways:
- Add a graphical user interface using Tkinter or PyQt
- Save semester records to a file or database
- Export results to a text file or PDF
- Support multiple universities and grading schemes
- Add subject categories like theory, lab, or audit courses
- Show performance trends across semesters
- Add exception-safe file handling and history tracking

18. Conclusion

The VIT Bhopal SGPA and CGPA Calculator is a practical Python project that demonstrates how programming can be used to solve a real academic problem. The project focuses on correctness, simplicity, and usability. It supports three modes of calculation, uses proper weighted formulas, and includes strong input validation to improve reliability.

Beyond the immediate usefulness of calculating grades, the project also reflects good programming practices such as modular design, reusable functions, and clear user interaction. Overall, this project is both a functional academic tool and a meaningful learning exercise in Python development.
