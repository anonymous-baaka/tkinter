import tkinter as tk

row=0
screenW=900
screenH=400

buttonH=2
buttonW=10

tbHeight=2
tbWidth=20

padX=10
padY=5

offsetY=40
def createWindow(width,height):
    root = tk.Tk()
    x = (root.winfo_screenmmwidth() // 2)
    y = (root.winfo_screenheight() // 2)
    root.geometry('{}x{}+{}+{}'.format(width,height,y,x))
    return root


root=createWindow(screenW,screenH)

#button -- do not touch
b1=tk.Button(root,text="ADD",command=lambda:createTB(4,row,root)) #add row
b1.configure(height=buttonH,width=buttonW)
#b1.pack(side=tk.BOTTOM)
b1.place(x=screenW//2,y=tbHeight+2*padY+buttonH+offsetY)

def submitClicked(tb,m,n):
    for i in range(n):
        input = tb[i].get("1.0",'end-1c')
        if input!="":
            print(input)

def createTB(n,m,root):         #number of tb, row
    '''create array of type text() of n size and place them in row m, create submit button, shift add button down'''
    tb=[tk.Text()]*n
    for i in range(n):
        tb[i]=tk.Text(root,height=tbHeight,width=tbWidth)   #cretae tb
        #tb[i].insert(tk.END,'{}'.format())                 #insert text into tb
        tb[i].insert(tk.END,'')
        #tb[i].grid(row=m)
        temp=tb[i]
        tb[i].grid(row=m,padx=padX,pady=padY,column=i)

    b1.grid(row=m+1,padx=padX,pady=padY,column=i//2+1)      #shift add button below

    b2 = tk.Button(root, text="Submit",command=lambda:submitClicked(tb,m,n))  # submit button crreate
    b2.configure(height=buttonH, width=buttonW)
    b2.grid(row=m,padx=padX,pady=padY,column=i+1)

    global row
    row+=1
    return tb
#tb1=createTB(4,row,root) #number of tb, row number

row+=1
root.mainloop()
