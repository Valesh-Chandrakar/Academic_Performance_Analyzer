# Academic-Performance-Analyzer

This C++ program is a student grading system that calculates the final grade of a student based on various components and weightages.
Here's a brief description of the project:

Classes: The program defines several classes to represent different aspects of a student's performance. These classes include:

student_details: Stores the student's name and roll number.
attendance: Calculates the attendance marks based on the total lectures attended compared to the total delivered.
ca: Collects and calculates Continuous Assessment (CA) marks based on the top two out of three CA scores.
mte: Records the Mid-Term Examination (MTE) marks and calculates the MTE marks based on the given weightage.
ete: Records the End-Term Examination (ETE) marks and calculates the ETE marks based on the given weightage.
final_result: Inherits from the above classes and calculates the final result, including the total weightage, and assigns a grade based on the final score.
Weightage: The program specifies different weightages for each component, as follows:

Attendance: 5%
CA: 25%
MTE: 20%
ETE: 50%
Calculations: The program calculates the attendance marks, CA marks (using the top two CA scores), MTE marks, and ETE marks based on the input values and weightages.

Grading: Based on the total weightage, the program assigns a grade to the student. Grades range from "O" (Outstanding) to "E" (Fail).

User Input: The program prompts the user to input various values, including attendance, CA scores, MTE, and ETE scores, as well as the student's name and roll number.

Output: After processing the input data, the program displays the student's name, roll number, marks in each component, the total weightage, and the final grade.

Overall, this program is a simple student grading system that demonstrates the use of classes and inheritance to calculate a student's final grade based on various academic components and weightages.

CONNECT TO GPT
To use AI features, please login to chat.openai.com
Not connecting?
Try to switch to Tab Mode, clear openai.com cookies, turn off VPN, or enter your OpenAI API Key
