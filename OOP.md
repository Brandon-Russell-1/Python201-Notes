
```
class Person:

    'Person base class'

  

    def __init__(self, name, age):

        self.name = name

        self.age = age

  

    def print_name(self):

        print("My name is {}".format(self.name))

    def print_age(self):

        print("My age is {}".format(self.age))

  

    def birthday(self):

        self.age += 1

  

class Hacker(Person):

  

    def __init__(self, name, age, cves):

        super().__init__(name, age)

        self.cves = cves

  

    def print_name(self):

        print ("My name is {} and I have {} CVEs".format(self.name, self.cves))

  

    def total_cves(self):

        return self.cves

  

bob = Person("bob", 30)

  

alice = Hacker("alice", 20, 5)

  

bob.print_name()

  

alice.print_name()


```

