myWindow is a subclass of frame

self sets the methods/attributes of the frame

types in python are based on a class

instance - DS generation: ID (someNumber);Class (RedFrame);Value (red), every object has id, type, value.  IS() returns objid equivalency

__init__ allows initialization of tk.Frame

self always needed when initialising

self is the whole object e.g. obj = MyWindow(root).pack(); obj(id) is passed to self keyword

creating an instance automatically invokes def __init__

nstances store attributes (values)

superclass <== subclass (base class <== dervied class)


PREVENTING openDebug = debug.openDebug


USING HELP FUNCTION IN PYTHON

FOR FRAME:
Methods defined here:

"
 |  #cnf={} can pass unto dictionary with resources listed in help
 |  __init__(self, master=None, cnf={}, **kw)

  Valid resource names: background, bd, bg, borderwidth, class,
 |      colormap, container, cursor, height, highlightbackground,
 |      highlightcolor, highlightthickness, relief, takefocus, visual, width.
"

My own class based on base class, we have to focus on __init__ when using help()

Interested in parameters in __init__


Multiple inheritence demonstrated

Every module, class, function have their own namespace - variables live here

Naming conflict:
from tkinter import *
def Canvas()
	pass
Canvas(my_win, width = 200) # no arg width

A scope is the portion of a program from where a namespace can be accessed directly without any prefix.

each module has its own global namespace(ns)
local ns when a function is called 

-----MY EXAMPLE-----

You can store attributes as part of the object

import tkinter as tk
from tkinter import ttk
from tkinter.messagebox import showinfo


class App(tk.Tk):
  def __init__(self):
    super().__init__()

    # configure the root window
    self.title('My Awesome App')
    self.geometry('300x50')

    # label
    self.label = ttk.Label(self, text='Hello, Tkinter!')
    self.label.pack()

    # button
    self.button = ttk.Button(self, text='Click Me')
    self.button['command'] = self.button_clicked
    self.button.pack()

  def button_clicked(self):
    showinfo(title='Information', message='Hello, Tkinter!')

if __name__ == "__main__":
  app = App()
  app.mainloop()

APPENDING OBJECTS TO LISTBOX

tk.Listbox(self,exportselection=False) #creates non-modal view

 def create_listbox(input_list,lst_obj):
                for i in input_list:
                    lst_obj.insert('end',i)

#reading
self.widget_entity.get(self.widget_entity.curselection())

