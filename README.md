from tkinter import *
from tkinter import ttk,messagebox

def calcurate():
	input1 = int(value1.get())
	input2 = int(value2.get())
	res = input1 + input2
	result.set(f'คำตอบคือ{res:d}')

def circle():
	input1 = int(rad.get())
	res = 3.142 * (input1**2)
	Result.set(f'ตอบ{res:,.2f}')

def add():
	messagebox.showerror('Error','เกิดข้อผิดพลาด')

def newfile():
    GUI2 = Tk()
    GUI2.title('calcurate program')
    GUI2.geometry('500x500')


GUI = Tk()

GUI.title('calcurate program')
GUI.geometry('500x500')

F1 = Frame(GUI)

Tab = ttk.Notebook(GUI)
Tab.pack()

F1 = Frame(Tab)
F2 = Frame(Tab)


Tab.add(F1,text='พื้นฐานการคำนวณ')
Tab.add(F2,text='วงกลม')

menubar = Menu(GUI)
GUI.config(menu=menubar)

file = Menu(menubar)
file.add_command(label='close',command=GUI.quit)
file.add_command(label='newfile',command=newfile)
menubar.add_cascade(label='File',menu=file)

calc = Menu(menubar,tearoff=0)
calc.add_command(label='การบวก')
calc.add_command(label='การลบ')
calc.add_command(label='การคูณ')
calc.add_command(label='การหาร')
menubar.add_cascade(label='การคำนวณ',menu=file)

FONT = ('Angsana New',24)

L1 = Label(F1,text='โปรแกรมคำนวณ',font=FONT)
L1.pack(pady=50)

value1 = StringVar()
value2 = StringVar()
result = StringVar()
result.set('--------')

E1 = ttk.Entry(F1,textvariable=value1,font=FONT)
E1.pack(ipady=10,ipadx=50)

E2 = ttk.Entry(F1,textvariable=value2,font=FONT)
E2.pack(ipady=10,ipadx=50,pady=50)

B1 = ttk.Button(F1,text='คำนวณ',command=calcurate)
B1.pack()

LResult = Label(F1,textvariable=result,font=FONT)
LResult.pack(pady=20)

#F2

F2L1 = Label(F2,text='คำนวณพื้นที่วงกลม',font=FONT)
F2L1.pack(pady=50)

rad = StringVar()
Result = StringVar()
Result.set('--------')

F2E1 = ttk.Entry(F2,textvariable=rad,font=FONT)
F2E1.pack(ipady=1,ipadx=30)

F2B1 = ttk.Button(F2,text='คำนวณ',command=circle)
F2B1.pack()

LResultF2 = Label(F2,textvariable=Result,font=FONT)
LResultF2.pack(pady=20)

GUI.mainloop()
