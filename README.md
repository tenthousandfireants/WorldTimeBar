# WorldTimeBar
world time in sydney, berlin, and newyork on the left side of your taskbar.

made in vs studio 2022, python 3.12, 


Source code here for if there is anything you wish to change.



# source code

/*

import tkinter as tk
from tkinter import Label
import pytz
from datetime import datetime
import pystray
from PIL import Image, ImageDraw, ImageFont
import threading

# Function to get the current time in different cities
def get_city_time(timezone):
    city_tz = pytz.timezone(timezone)
    city_time = datetime.now(city_tz)
    return city_time.strftime('%H:%M')

# Function to update the displayed time
def update_clock():
    sydney_time = get_city_time('Australia/Sydney')
    berlin_time = get_city_time('Europe/Berlin')
    ny_time = get_city_time('America/New_York')

    # Update the label text
    time_label.config(text=f"SY: {sydney_time} | BR: {berlin_time} | NY: {ny_time}")
    
    # Refresh the clock every 60 seconds (1 minute)
    root.after(60000, update_clock)

# Function to create a bold "T" icon for the system tray
def create_tray_icon():
    image = Image.new('RGB', (64, 64), "black")  # Black background
    draw = ImageDraw.Draw(image)

    # Load a custom TrueType font (you can specify a font path if needed)
    font_path = "C:/Windows/Fonts/arialbd.ttf"  # Adjust this path to your font
    font = ImageFont.truetype(font_path, 48)  # Adjust the size to fit the icon

    # Define the text and calculate its bounding box
    text = "T"
    bbox = draw.textbbox((0, 0), text, font=font)
    text_width, text_height = bbox[2] - bbox[0], bbox[3] - bbox[1]

    # Center the text within the 64x64 icon
    position = ((64 - text_width) // 2, (64 - text_height) // 2)

    # Draw the "T" in white
    draw.text(position, text, font=font, fill="white")

    return image

# Function to quit the app using the tray icon
def on_quit(icon, item):
    icon.stop()
    root.quit()  # Close the Tkinter window

# Set up the tray icon using pystray
def setup_tray_icon():
    icon = pystray.Icon("WorldTime", create_tray_icon(), menu=pystray.Menu(
        pystray.MenuItem("Quit WorldTime Bar", lambda: on_quit(icon, None))
    ))

    icon.run()

# Initialize Tkinter root window
root = tk.Tk()

# Set window size and position above the taskbar
root.geometry('400x50+10+1040')  # Adjust the y-offset to position it perfectly
root.config(bg='black')
root.overrideredirect(True)  # Remove title bar
root.attributes('-topmost', True)  # Keep on top

# Ensure the window stays on top
def keep_window_on_top():
    root.lift()  # Lift the window to the top
    root.after(2000, keep_window_on_top)  # Keep checking every 2 seconds

# Start the "always on top" behavior
keep_window_on_top()

# Create a label to show the time for each city
time_label = Label(root, text="", font=("Helvetica", 18), fg="red", bg="black")
time_label.pack()

# Start clock updates
update_clock()

# Start the system tray in a separate thread so it doesn't block the Tkinter main loop
def run_tray():
    tray_thread = threading.Thread(target=setup_tray_icon, daemon=True)
    tray_thread.start()

run_tray()

# Start the Tkinter main loop
root.mainloop()

*/

///-----------------------------------------------------------------------------------------





