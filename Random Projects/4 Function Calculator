from tkinter import *
from tkinter.ttk import *

class Calculator(Tk):

    def __init__(self):
        super().__init__()

        self.screen_var = StringVar()
        self.screen_var.set("0")

        self.var_1 = StringVar()
        self.var_1.set("")
        self.var_1_pos = "open"
        
        self.var_2 = StringVar()
        self.var_2.set("")
        self.var_2_pos = "open"

        self.op_var = StringVar()
        self.op_var.set("")

        self.create_widgets()


#BUTTON INITIALIZATION:
    def create_widgets(self):

        self.title("Calculator")

        self.frame = Frame(self, height = 100, width = 100)
        self.frame.grid()

        self.screen = Label(self.frame, text=self.screen_var.get())
        self.screen.grid(row = 0, column = 3)

        self.Button_1 = Button(self.frame, text = "1", command=lambda: self.var_set(1))
        self.Button_1.grid(row = 1, column = 1)

        self.Button_2 = Button(self.frame, text = "2", command=lambda: self.var_set(2))
        self.Button_2.grid(row = 1, column = 2)

        self.Button_3 = Button(self.frame, text = "3", command=lambda: self.var_set(3))
        self.Button_3.grid(row = 1, column = 3)

        self.Button_4 = Button(self.frame, text = "4", command=lambda: self.var_set(4))
        self.Button_4.grid(row = 2, column = 1)

        self.Button_5 = Button(self.frame, text = "5", command=lambda: self.var_set(5))
        self.Button_5.grid(row = 2, column = 2)

        self.Button_6 = Button(self.frame, text = "6", command=lambda: self.var_set(6))
        self.Button_6.grid(row = 2, column = 3)

        self.Button_7 = Button(self.frame, text = "7", command=lambda: self.var_set(7))
        self.Button_7.grid(row = 3, column = 1)

        self.Button_8 = Button(self.frame, text = "8", command=lambda: self.var_set(8))
        self.Button_8.grid(row = 3, column = 2)

        self.Button_9 = Button(self.frame, text = "9", command=lambda: self.var_set(9))
        self.Button_9.grid(row = 3, column = 3)

        self.Button_0 = Button(self.frame, text = "0", command=lambda: self.var_set(0))
        self.Button_0.grid(row = 4, column = 2)

        self.Button_div = Button(self.frame, text = "/", command=lambda: self.div_var())
        self.Button_div.grid(row = 1, column = 4)

        self.Button_mul = Button(self.frame, text = "x", command=lambda: self.mul_var())
        self.Button_mul.grid(row = 2, column = 4)

        self.Button_sub = Button(self.frame, text = "-", command=lambda: self.sub_var())
        self.Button_sub.grid(row = 3, column = 4)

        self.Button_add = Button(self.frame, text = "+", command=lambda: self.add_var())
        self.Button_add.grid(row = 4, column = 4)

        self.Button_eq = Button(self.frame, text = "=", command=lambda: self.calc(self.var_1.get(), self.var_2.get(), self.op_var.get()))
        self.Button_eq.grid(row = 4, column = 3)
        
        self.Button_deci = Button(self.frame, text = ".", command=lambda: self.var_set("."))
        self.Button_deci.grid(row = 4, column = 1)

        self.Button_clr = Button(self.frame, text = "Clear", command=lambda: self.clear())
        self.Button_clr.grid(row = 0, column = 4)

        self.Button_ce = Button(self.frame, text = "CE", command=lambda: self.ce())
        self.Button_ce.grid(row = 0, column = 1)

#TESTING BUTTON INITIALIZATION:
##        self.op_test_Button = Button(self.frame, text="op", command=lambda: self.op_test())
##        self.op_test_Button.grid(row = 5, column = 1)
##
##        self.op_test_Button = Button(self.frame, text="var1", command=lambda: self.var1_test())
##        self.op_test_Button.grid(row = 5, column = 2)
##
##        self.op_test_Button = Button(self.frame, text="var2", command=lambda: self.var2_test())
##        self.op_test_Button.grid(row = 5, column = 3)


#CLEAR BUTTON METHOD:
    def clear(self):
        self.screen_var.set(0)
        self.var_1.set("")
        self.var_1_pos = "open"
        self.var_2.set("")
        self.var_2_pos = "open"
        self.op_var.set("")
        self.screen["text"] = self.screen_var.get()


#CLEAR ENTRY BUTTON METHOD:
    def ce(self):
        if self.var_2.get() == "":
            self.screen_var.set(0)
            self.var_1.set("")
            self.screen["text"] = self.screen_var.get()
        else:
            self.screen_var.set(0)
            self.var_2.set("")
            self.screen["text"] = self.screen_var.get()
        

#OPERATOR METHODS:
    def div_var(self):
        self.op_var.set("/")
        self.var_1_pos = "closed"

    def mul_var(self):
        self.op_var.set("x")
        self.var_1_pos = "closed"

    def sub_var(self):
        self.op_var.set("-")
        self.var_1_pos = "closed"

    def add_var(self):
        self.op_var.set("+")
        self.var_1_pos = "closed"
        

#VAR1/VAR2 NUMBER BUTTON INPUT SETTER:
    def var_set(self, num):
        if num == ".":
            if self.var_1_pos == "open":
                if "." not in self.var_1.get():
                    self.var_1.set(self.var_1.get() + str(num))
                    self.screen_var.set(self.var_1.get())
                    self.screen["text"] = self.screen_var.get()
            elif self.var_2_pos == "open" and self.var_1_pos == "closed":
                if "." not in self.var_2.get():
                    self.var_2.set(self.var_2.get() + str(num))
                    self.screen_var.set(self.var_2.get())
                    self.screen["text"] = self.screen_var.get()
        elif self.op_var.get() == "":
            self.var_1.set(self.var_1.get() + str(num))
            self.screen_var.set(self.var_1.get())
            self.screen["text"] = self.screen_var.get()
        elif self.var_1_pos == "closed" and self.op_var.get() != "":
            if self.var_2_pos == "open":
                self.var_2.set(self.var_2.get() + str(num))
                self.screen_var.set(self.var_2.get())
                self.screen["text"] = self.screen_var.get()

                                       
#BACKEND CALCULATION AND SCREEN SET:
    def calc(self, var1, var2, op_var):
        if self.var_2.get() != "":
            if op_var == "/":
                if var2 == "0":
                    self.screen_var.set("Error")
                    self.screen["text"] = self.screen_var.get()
                    self.var_1.set("")
                    self.var_1_pos = "open"
                    self.var_2.set("")
                    self.var_2_pos = "open"
                    self.op_var.set("")
                else:
                    out = float(var1)/float(var2)
                    self.screen_var.set(str(out))
                    self.screen["text"] = self.screen_var.get()
                    self.var_1.set(str(out))
                    self.var_2.set("")
                    self.var_2_pos = "open"
                    self.op_var.set("")
            elif op_var == "x":
                out = float(var1)*float(var2)
                self.screen_var.set(str(out))
                self.screen["text"] = self.screen_var.get()
                self.var_1.set(str(out))
                self.var_2.set("")
                self.var_2_pos = "open"
                self.op_var.set("")
            elif op_var == "-":
                out = float(var1)-float(var2)
                self.screen_var.set(str(out))
                self.screen["text"] = self.screen_var.get()
                self.var_1.set(str(out))
                self.var_2.set("")
                self.var_2_pos = "open"
                self.op_var.set("")
            elif op_var == "+":
                out = float(var1)+float(var2)
                self.screen_var.set(str(out))
                self.screen["text"] = self.screen_var.get()
                self.var_1.set(str(out))
                self.var_2.set("")
                self.var_2_pos = "open"
                self.op_var.set("")

        
##TESTING BUTTONS FOR VAR1/VAR1/OP_VAR:
##    def op_test(self):
##        self.screen_var.set(self.op_var.get())
##        self.screen["text"] = self.screen_var.get()
##
##    def var1_test(self):
##        self.screen_var.set(float(self.var_1.get()))
##        self.screen["text"] = self.screen_var.get()
##
##    def var2_test(self):
##        self.screen_var.set(float(self.var_2.get()))
##        self.screen["text"] = self.screen_var.get()
    


root = Calculator()
root.resizable(width=False, height=False)
root.mainloop()

