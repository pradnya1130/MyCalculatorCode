import tkinter as tk

# Create the main window
window = tk.Tk()
window.title("Calculator")

# Styling variables
bg_color = "#F0F0F0"
button_bg_color = "#D3D3D3"
button_fg_color = "#000000"
button_active_bg_color = "#A9A9A9"
button_width = 8
button_height = 3
button_font = ("Arial", 12, "bold")
entry_font = ("Arial", 20, "bold")

# Function to handle button clicks
def handle_click(event):
    button_text = event.widget.cget("text")
    current_expression = result_entry.get()

    if button_text == "C":
        result_entry.delete(0, tk.END)
    elif button_text == "=":
        try:
            result = eval(current_expression)
            result_entry.delete(0, tk.END)
            result_entry.insert(tk.END, str(result))
        except:
            result_entry.delete(0, tk.END)
            result_entry.insert(tk.END, "Error")
    else:
        result_entry.insert(tk.END, button_text)


# Configure window background color
window.configure(bg=bg_color)

# Create entry widget to display the result
result_entry = tk.Entry(
    window, font=entry_font, width=20, bd=5, justify=tk.RIGHT
)
result_entry.grid(row=0, column=0, columnspan=4, pady=10, padx=10)

# Create buttons
buttons = [
    ("7", 1, 0),
    ("8", 1, 1),
    ("9", 1, 2),
    ("/", 1, 3),
    ("4", 2, 0),
    ("5", 2, 1),
    ("6", 2, 2),
    ("*", 2, 3),
    ("1", 3, 0),
    ("2", 3, 1),
    ("3", 3, 2),
    ("-", 3, 3),
    ("0", 4, 0),
    (".", 4, 1),
    ("C", 4, 2),
    ("+", 4, 3),
    ("=", 5, 0, 1, 4)  # Spanning two columns
]

for button in buttons:
    text, row, column = button[0], button[1], button[2]
    columnspan = button[3] if len(button) > 3 else 1
    btn = tk.Button(
        window,
        text=text,
        width=button_width,
        height=button_height,
        bg=button_bg_color,
        fg=button_fg_color,
        activebackground=button_active_bg_color,
        font=button_font,
    )
    btn.grid(
        row=row,
        column=column,
        columnspan=columnspan,
        padx=5,
        pady=5,
        ipadx=5,
        ipady=5,
    )
    btn.bind("<Button-1>", handle_click)

# Start the main loop
window.mainloop()
