class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade


class Model:
    def __init__(self):
        self.students = []

    def add_student(self, student):
        self.students.append(student)

    def get_students(self):
        return self.students


class ViewModel:
    def __init__(self, model):
        self.model = model

    def get_student_info(self):
        students = self.model.get_students()
        return [f"Name: {student.name}, Age: {student.age}, Grade: {student.grade}" for student in students]


class View:
    def display_students(self, student_info):
        for info in student_info:
            print(info)


# 示例用法
model = Model()
student1 = Student("Eva", 20, "A")
student2 = Student("Max", 21, "B")
model.add_student(student1)
model.add_student(student2)

view_model = ViewModel(model)
student_info = view_model.get_student_info()

view = View()
view.display_students(student_info)
