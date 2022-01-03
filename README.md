from tkinter import *
from tkinter import messagebox
from pytube import *
from msvcrt import *
from tkinter.messagebox import showinfo
import random
pro = Tk()
pro.geometry('800x450+280+100')
pro.resizable(False,False)
pro.title('youtube video download')
f3= Frame(pro , width=570 , height=450 , bg='#0B2F3A').place(x=0,y=60)
title = Label (pro , text='youtube video download' , fg= 'gold' , bg= 'black' , font=('tajawal',16,'bold'))
title.pack(fill=X)
f1= Frame(pro , width=230 , height=420 , bg='#0B2F3A')
f1.place(x=570 ,y=30)
f2=Frame(pro,width=570 , height= 30 , bg='#0B2F3A').place(x=0 , y=30)
t1 = Label(f3,text='URL ', fg='#DBA901' , bg= '#0B2F3A' , font=('tajawal', 12,'bold')).place(x=285 , y=55)

ggr= StringVar()
gg= StringVar()
iink_enter = Entry(f3,width=30,textvariable=ggr).place(x=210 , y= 150)
iink_enter = Entry(f3,width=30,textvariable=gg).place(x=210 , y= 250)

list= ["0.mp3","2.mp3","3.mp3","4.mp3","5.mp3","6.mp3","7.mp3","8.mp3","9.mp3","1.mp3"]
number = ""
number = number+ random.choice(list)


def Download():
    url=YouTube(str(ggr.get()))
    video= url.streams.get_highest_resolution()
    video.download()
    showinfo(title="Done", message="successfully")


def downloaderr():
    url = YouTube(str(gg.get()))
    video = url.streams.get_audio_only()
    video.download(filename=number)
    showinfo(title="done", message='successfully')


Button(f1,text = 'DOWNLOAD', font = 'arial 15 bold' ,bg = '#0B2F3A',fg="gold" , padx = 2, command = Download).place(x=15 ,y = 110)
Button(f1,text = 'DOWNLOAD', font = 'arial 15 bold' ,bg = '#0B2F3A',fg="gold" , padx = 2, command =  downloaderr ).place(x=15 ,y = 210)
title2=Label(f1, text='MP4 DOWNLOAD' , bg='#0B2F3A', fg= 'gold' , font=('tajawal', 12,'bold'))
title2.place(x=13,y=80)
title2=Label(f1, text='MP3 DOWNLOAD' , bg='#0B2F3A', fg= 'gold' , font=('tajawal', 12,'bold'))
title2.place(x=13,y=185)



pro.mainloop()
