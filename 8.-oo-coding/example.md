# Example

Back in 2022, a classgroup asked me to go through an OO example. I created the following file on the fly during an e-delivery session. It is for a personnel system for a University.

We are all people and people have particular characteristics, regardless on what they do.

Child classes of people are Staff, and Students.

But Staff also has child classes, Academic Staff and Admin Staff.&#x20;

At each class, I keep only the methods and properties most appropriate to that level.

Work your way through the structure and make sure it makes sense!

```
class People():
    # Constructor, called whenever an instance of the class is created.
    def __init__(self) -> None:
        print("Running constructor for People")
        self.dob = None
        self.title = None
        self.first_name = None
        self.middle_initial = None
        self.surname = None  

    def find_age(self):
        pass

class Staff(People):
    def __init__(self) -> None:
        # Call back to the parent class
        print("Running constructor for Staff")
        People.__init__(self)
        self.staff_id = None
        self.start_date = None
        self.debug = True

    def length_of_service(self):
        if self.debug:
            print("Staff->Length_of_service")
        pass

class Student(People):
    def __init__(self) -> None:
        # Call back to the parent class
        print("Running constructor for Student")
        People.__init__(self)
        self.student_id = None
        self.start_date = None

    def length_of_attendance(self):
        print("Yoo hoo!")
        pass

class AcademicStaff(Staff):
    def __init__(self) -> None:
        # Call back to the parent class
        print("Running constructor for AcademicStaff")
        Staff.__init__(self)
        self.primary_qualification = None
        self.academic_grade = None
   
    def academic_cbt(self):
        pass

class AdminStaff(Staff):
    def __init__(self) -> None:
        # Call back to the parent class
        print("Running constructor for AdminStaff")
        Staff.__init__(self)
        self.primary_qualification = None
        self.job_description = None
        self.department = None
   
    def academic_cbt(self):
        pass
```
