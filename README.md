
from tkinter import *
class Calculator:
from tkinter import *
class Calculator:

    def __init__(self):

        self.root=Tk()

        self.result=Label()
        self.result.grid(row=0,column=0)

        Button(text="1", bg="yellow",width=6,height=3,command=lambda:self.get_number("1")).grid(row=1,column=0)
        Button(text="2", bg="green",width=6,height=3,command=lambda:self.get_number("2")).grid(row=1,column=1)
        Button(text="3", bg="red", width=6, height=3,command=lambda:self.get_number("3")).grid(row=1, column=2)
        Button(text="+", bg="blue",fg="white", width=6, height=3,command=lambda:self.get_operator("+")).grid(row=1, column=3)

        Button(text="4", bg="green", width=6, height=3,command=lambda:self.get_number("4")).grid(row=2, column=0)
        Button(text="5", bg="red", width=6, height=3,command=lambda:self.get_number("5")).grid(row=2, column=1)
        Button(text="6", bg="blue", width=6, height=3,command=lambda:self.get_number("6")).grid(row=2, column=2)
        Button(text="-", bg="yellow",fg="white", width=6, height=3,command=lambda:self.get_operator("-")).grid(row=2, column=3)

        Button(text="7", bg="red", width=6, height=3,command=lambda:self.get_number("7")).grid(row=3, column=0)
        Button(text="8", bg="blue", width=6, height=3,command=lambda:self.get_number("8")).grid(row=3, column=1)
        Button(text="9", bg="yellow", width=6, height=3,command=lambda:self.get_number("9")).grid(row=3, column=2)
        Button(text="*", bg="green",fg="white", width=6, height=3,command=lambda:self.get_operator("*")).grid(row=3, column=3)

        Button(text="0",bg="blue",width=6,height=3,command=lambda:self.get_number("0")).grid(row=4,column=0)
        Button(text="/",bg="yellow",width=6,height=3,command=lambda:self.get_operator("/")).grid(row=4,column=1)
        Button(text="c", bg="green", width=6, height=3,command=lambda:self.clear()).grid(row=4, column=2)
        Button(text="=", bg="red",fg="white", width=6, height=3,command=lambda:self.get_result()).grid(row=4, column=3)

        self.root.mainloop()

    def get_number(self,number):
        new_number=self.result['text']+number
        self.result.configure(text=new_number)

    def get_operator(self,operator):

        self.first_num=float(self.result['text'])
        self.result.configure(text="")
        self.operator=operator

    def clear(self):
        self.result.configure(text="")

    def get_result(self):

        self.second_num=float(self.result['text'])
        if self.operator=="+":
            self.result.configure(text=str(self.first_num + self.second_num))
        elif self.operator=="-":
            self.result.configure(text=str(self.first_num - self.second_num))


        elif self.operator=="*":
            self.result.configure(text=str(self.first_num * self.second_num))
        else:
            if self.second_num==0:
                self.result.configure(text="sonakshi")
            else:
                self.result.configure(text=str(self.first_num/self.second_num))


obj=Calculator()
