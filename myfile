import tkinter as tk
import tkinter.ttk as ttk

def changeframe(frame):
  frame.tkraise()

def check_data(IMO_number, password):
    print("Logged In succesfully.")
    changeframe(frame2)
    
def progresscmd(i=0):
  if i <= 100:
    p_var2.set(i)
    progressbar.update()
    window.after(10, progresscmd, i + 1)
  else:
    if wind < 14 and rain < 30:
      weather_text = f"The weather is appropriate. \n<Weather now> \n rain: {wind}, wind: {rain}"
      ttk.Label(frame5, text=weather_text).pack()
      changeframe(frame6)
    else: 
      ttk.Label(frame5, text="Sorry. The weather is not appropriate.").pack()
    
def check_ship_length(verti):
  verti = ship_length.get()
  if verti == "":
    print("please enter the ship length.")
    return
  else: 
    verti=int(verti)
    possible_place=[] 
    if verti*13<3000: possible_place.append('1')
    elif 3000<=verti*13<4000: possible_place.append('2')
    elif 4000<=verti*13: possible_place.append('3')
    
  return possible_place
  return changeframe(frame1)

window = tk.Tk()
window.title("Ferry program (for captain)") #프로그램이름선언
window.geometry("800x400") #창크기설정

frame1 = tk.Frame(window)
frame2 = tk.Frame(window)
frame3 = tk.Frame(window)
frame4 = tk.Frame(window)
frame5 = tk.Frame(window)
frame6 = tk.Frame(window)
frame7 = tk.Frame(window)

frame1.grid(row=0, column=0, sticky="nsew")
frame2.grid(row=0, column=0, sticky="nesw")
frame3.grid(row=0, column=0, sticky="nesw")
frame4.grid(row=0, column=0, sticky="nesw")
frame5.grid(row=0, column=0, sticky="nesw")
frame6.grid(row=0, column=0, sticky="nesw")
frame7.grid(row=0, column=0, sticky="nesw")

changeframe(frame1)

IMO_number, password = tk.StringVar(), tk.StringVar()
ttk.Label(frame1, text = "IMO number:").grid(row = 0, column = 0, padx = 10, pady = 10)
ttk.Label(frame1, text = "Password:").grid(row = 1, column = 0, padx = 10, pady = 10)
ttk.Entry(frame1, textvariable=IMO_number).grid(row = 0, column = 1, padx = 10, pady = 10)
ttk.Entry(frame1, textvariable=password).grid(row = 1, column=1, padx=10, pady=10)
ttk.Button(frame1, text = "Login", command=check_data).grid(row=2, column=1, padx=10, pady=10)

hello_label = tk.Label(frame2, text="Welcome to Ferry Program.\nPress 'Start' button to start the program.")
hello_label.pack() #환영말선언(시작버튼line42에있음)
start_button = tk.Button(frame2, padx=10, pady=10, text="Start", command=lambda:changeframe(frame3))
start_button.pack() #환영말선언후시작버튼

select_label = tk.Label(frame3, text="Please select the port.") #항구선택
select_label.pack()
values1 = ['Pusan Newport International Terminal', 'Incheon International Terminal'] #선택지1
select_combobox=ttk.Combobox(frame3, height=5, width=20, values=values1)
select_combobox.pack()
next_button = tk.Button(frame3, padx=10, pady=10, text="Check the weather", command=progresscmd)

p_var2 = tk.DoubleVar()
progressbar = ttk.Progressbar(frame4, maximum=100, length=300, mode="determinate", variable=p_var2) #loading창설정
progressbar.pack()

window.after(0, progresscmd)

wind = 10
rain = 20

ship_length = tk.StringVar()
ttk.Label(frame6, text = "Length of the ship:").grid(row = 1, column = 0, padx = 10, pady = 10)
ttk.Entry(frame6, textvariable=ship_length).grid(row = 1, column=1, padx=10, pady=10)
ttk.Button(frame6, text="OK", command=check_ship_length).grid(row=2, column=1, padx=10, pady=10)

changeframe(frame1)
tk.mainloop() #끝
