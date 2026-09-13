
# this block of code is just a dictionary for each student and their 3 grades stored.
student_grades = {
    "Alice": [85, 90, 78],
    "Bob": [92, 88, 95],
    "Charlie": [70, 80, 82],
}

# this block averages out the the grades for each student by suming up the 3 number grades and then divides it by 3 to get the average.
student_averages = {
    student: sum(grades) / len(grades) for student, grades in student_grades.items()
    }

# this block of code assigns a letter grade to each student based on their average grade and prints out the results.
student_letter_grades = {}
for student, average in student_averages.items():
    if average >= 90:
        letter_grade = "A"
    elif average >= 80:
        letter_grade = "B"
    elif average >= 70:
        letter_grade = "C"
    elif average >= 60:
        letter_grade = "D"
    else:
        letter_grade = "F"
    student_letter_grades[student] = letter_grade
    print()
    print(f"{student} has an average grade of {average:.2f}, Which is a {letter_grade}")

# this block of code finds the student with the highest average grade.
top_student = ""
top_average = 0
for student, average in student_averages.items():
    if average > top_average:
        top_student = student
        top_average = average

# this block of code calculates the classes overall average and counts how many students passed the class with a grade of 70 or higher.
class_average = sum(student_averages.values()) / len(student_averages)
passing_count = 0
for letter_grade in student_letter_grades.values():
    if letter_grade in ("A", "B", "C"):
        passing_count += 1

print()
print(f"Top student: {top_student} with an average grade of {top_average:.2f}")
print()
print(f"Overall class average: {class_average:.2f}")
print()
print(f"Number of students who passed: {passing_count}")
