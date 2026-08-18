# Student-Grade-Management-System
Stores student names and marks, calculates average, and assigns letter grades.
students = {}

def add_student(name, marks):
    students[name] = marks

def get_grade(avg):
    if avg >= 90: return "A"
    elif avg >= 75: return "B"
    elif avg >= 60: return "C"
    elif avg >= 40: return "D"
    return "F"

def report(name):
    marks = students[name]
    avg = sum(marks) / len(marks)
    print(f"{name}: Avg={avg:.1f}, Grade={get_grade(avg)}")

while True:
    cmd = input("\nadd/report/list/quit: ").strip().lower()
    if cmd == "add":
        name = input("Name: ")
        marks = list(map(int, input("Marks (space separated): ").split()))
        add_student(name, marks)
    elif cmd == "report":
        report(input("Name: "))
    elif cmd == "list":
        for n in students: report(n)
    elif cmd == "quit":
        break
