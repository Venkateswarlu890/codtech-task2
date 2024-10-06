# codtech-task2


class Student:
    def init(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        self.grades[subject] = grade

    def calculate_average(self):
        total = sum(self.grades.values())
        average = total / len(self.grades)
        return average

    def get_letter_grade(self):
        average = self.calculate_average()
        if average >= 90:
            return "A"
        elif average >= 80:
            return "B"
        elif average >= 70:
            return "C"
        elif average >= 60:
            return "D"
        else:
            return "F"

    def display_grades(self):
        print(f"Student Name: {self.name}")
        print("Subject\tGrade")
        for subject, grade in self.grades.items():
            print(f"{subject}\t{grade}")
        print(f"Average Grade: {self.calculate_average():.2f}")
        print(f"Letter Grade: {self.get_letter_grade()}")

# Get user input for student name
student_name = input("Enter student name: ")

# Create a new student object
student = Student(student_name)

# Get user input for grades
while True:
    subject = input("Enter subject (or 'quit' to exit): ")
    if subject.lower() == "quit":
        break
    grade = float(input("Enter grade: "))
    student.add_grade(subject, grade)

# Display student grades and statistics
student.display_grades()
