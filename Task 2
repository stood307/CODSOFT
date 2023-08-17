import tkinter as tk

def button_click(event):
    text = event.widget.cget("text")
    
    if text == "=":
        try:
            result = eval(screen.get())
            screen.set(result)
        except Exception as e:
            screen.set("Error")
    elif text == "C":
        screen.set("")
    else:
        screen.set(screen.get() + text)

root = tk.Tk()
root.geometry("400x600")
root.title("Rakesh's Calculator")

screen = tk.StringVar()
screen.set("")

entry = tk.Entry(root, textvar=screen, font=("Helvetica", 24), bd=10, insertwidth=4, width=14, justify="right")
entry.pack(padx=10, pady=10)

button_frame = tk.Frame(root)
button_frame.pack()

buttons = [
    ("7", 1, 0), ("8", 1, 1), ("9", 1, 2), ("/", 1, 3),
    ("4", 2, 0), ("5", 2, 1), ("6", 2, 2), ("*", 2, 3),
    ("1", 3, 0), ("2", 3, 1), ("3", 3, 2), ("-", 3, 3),
    ("0", 4, 0), (".", 4, 1), ("C", 4, 2), ("+", 4, 3),
    ("=", 5,3)  # Added rowspan and columnspan values for the equal sign button
]

for (text, row, col, *span) in buttons:
    rowspan = columnspan = 1
    if span:
        rowspan, columnspan = span
    button = tk.Button(button_frame, text=text, font=("Helvetica", 19), relief="ridge", padx=25, pady=25)
    button.grid(row=row, column=col, rowspan=rowspan, columnspan=columnspan)
    button.bind("<Button-1>", button_click)

root.mainloop()

