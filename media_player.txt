import click
import vlc
import time
import keyboard as k
from tkinter import *
from tkinter import filedialog as fd

def open():
    filetypes = (
        ('video files', '*.mp4'),
        ('All files', '*.*')
    )
    filename = fd.askopenfilename(
        title='Open a file',
        initialdir='/Desktop',
        filetypes=filetypes)
    media_player = vlc.MediaPlayer(filename)
    media_player.play()
    if k.read_key()=='q':
        media_player.stop()




window= Tk()
window.geometry("400x300")
window.configure(background="#072227")
font= ("arial",20 )
font2=("arial", 12)
label= Label(window, text="Video Player", font=font, fg="#92A9BD", bg="#072227")
label.pack()
label3= Label(window, text="Press Q to quit the player", font=font2, fg="#92A9BD", bg="#072227")
label3.pack()
label2= Label(window, text="Choose any Video to Play", font=font2, fg="#92A9BD", bg="#072227")
label2.place(x=40,y=140)
but=Button(window, text="Browse" ,command=open).place(x=240,y=140)
window.mainloop()
