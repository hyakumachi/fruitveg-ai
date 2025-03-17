
# Disclaimer
> - This is structured in order, from top to bottom. 
> - This is using python 3.12.1
> - I will not be adding all expected outputs. 

> 3/6/2025

# Installation of [Kivy: Cross-platform Python Framework for GUI apps Development](https://kivy.org/)
```cmd
pip install kivy
```

# Initial introduction
This demonstrates running the app
```python title:project/sameple1.py
from kivy.app import App #import the App class module
from kivy.uix.button import Button #importing button widget

class FirstApp(App): 
	def build(self):
		return Button(text="Hello World!")

if __name__ == '__main__':
	FirstApp().run()




```


# Demonstration of other widgets and BoxLayout
```python title:project/sameple1.py
from kivy.app import App # Import the App class module
from kivy.uix.button import Button # Importing button widget
from kivy.uix.boxlayout import BoxLayout # Button Widget
from kivy.uix.label import Label # Label Widget

class LayoutApp(App): #Class
	def build(self): #Method
		layout = BoxLayout(orientation="vertical") #Creates a container, Orientation is vertial by default (Top to Bottom)
		self.label = Label(text="Press the button!")
		btn = Button(text="Click me!") # text parameter is the caption
		btn.bind(on_press=self.update_label)
		layout.add_widget(self.label)
		layout.add_widget(btn)
		return layout
		
	def update_label(self, instance): 
		self.label.text = 'Button was pressed' #Changes the text of the label to this.

if __name__ == "__main__": 
	LayoutApp().run() # Run the class Layout App

```
## Expected Output: 
![](https://i.imgur.com/lBnLbhi.png)


# Image Widget Demonstration
Demonstration of the Image Widget

## Step 1:
```python title:project/example1.py
from kivy.app import App # Import the App class module
from kivy.uix.boxlayout import BoxLayout # Button Widget
from kivy.uix.image import Image # Using the widget image

class ImageApp(App): #Class
	def build(self): #Method
		layout = BoxLayout(orientation="vertical") # Creates a layout/window
		self.image = Image(source="abc.png") # Create an Image widget
		layout.add_widget(self.image) #Add the widget to the layout
		return layout

if __name__ == "__main__": 
	ImageApp().run() # Run the class Layout App

```

## Step 2: 
- Add an image into the project folder
- Rename it to abc (Should be a .png file)

# Camera Widget
## Step 1:
```python title:project/example1.py
from kivy.app import App # Import the App class module
from kivy.uix.boxlayout import BoxLayout # Button Widget
from kivy.uix.image import Image # Using the widget image

class CameraApp(App): #Class
	def build(self): #Method
		layout = BoxLayout(orientation="vertical") # Creates a layout/window
		self.camera = Camera(resoution=(640, 480), play=False)
		
		self.btn = Button(text="Start", size_hint=(1, 0.1)) # Argument 1: Width (100% width), Argument 2: Height (10% height)
		self.btn.bind(on_press=self.toggle_camera)
		layout.add_widget(self.camera)
		layout.add_widget(sekf.btn)
		return layout

	def toggle_camera(self, instance):
		self.camera.play = not self.camera.play
		self.btn.text = 'Stop' if self.camera.play else 'Start'

if __name__ == "__main__": 
	CameraApp().run() # Run the class Layout App

```