<pre class="ascii">
┌───────────────────────────────────┐ ┌────────────────────────────────────┐ ┌──────────────────────────────────────┐
|                      _    __      | | Latest posts                       | | NAV                                  |
|    _ __  _   _  __ _| |_ / /_     | │ - <a href="/blogs/pyqt.md">PyQt</a>                             │ │ - <a href="/blogs/html.md">HTML</a>                               │
|   | '_ \| | | |/ _` | __| '_ \    | │ - <a href="/blogs/html.md">HTML</a>                             │ │ - <a href="/blogs/pyqt.md">PyQt</a>                               │
|   | |_) | |_| | (_| | |_| (_) |   | │ - ...                              │ │ - <a href="https://github.com/0-harshit-0/">About</a>                              │
|   | .__/ \__, |\__, |\__|\___/    | │                                    │ │ - <a href="/blogs/nav.md">Nav</a>                                │
|   |_|    |___/    |_|             | │                                    │ │                                      │
└───────────────────────────────────┘ └────────────────────────────────────┘ └──────────────────────────────────────┘
</pre>


- [Skip to learning resources](#more-reading-material).
- The PyQT library serves as a bridge for C++ Qt framework.
- You can use it to create feature-rich cross-platform GUI (I've only tried on Windows 😜). Useful when CLI is not enough.
- Python also has tkinter, which relies on the TK GUI toolkit. I loved working with PyQt more than tkinter, because it offers useful toolings and full-featured widgets/layouts, so there's less boilerplate to manage.


## Widgets

- You will work with Widgets all the time. They are building blocks of your Interface.

- A widget can be a control (like a label, button, or text input) or a container that holds other widgets (like a plain QWidget or a QFrame).


## Layouts

- Layouts are very useful and provides an easy way to organize widgets.

- Layouts automatically arrange widgets inside a container and keep the UI usable when the window is resized.

- PyQt provides various kind of layouts. QGridLayout, QVBoxLayout, QHBoxLayout, QFormLayout, are just a few examples.

- You can _"polish"_ a layout by nesting layouts, controlling padding with setContentsMargins(...), controlling gaps with setSpacing(...), and using stretch/alignment so important areas expand while others stay compact.


```py

# example

import sys

from PyQt6.QtWidgets import (
    QApplication, QMainWindow, QWidget,
    QVBoxLayout, QHBoxLayout,
    QLabel, QLineEdit, QPushButton
)
from PyQt6.QtCore import Qt


def build_screen(parent: QWidget) -> QWidget:
    screen = QWidget(parent)

    root = QVBoxLayout(screen)
    root.setContentsMargins(12, 12, 12, 12)
    root.setSpacing(10)

    title = QLabel("API Settings", screen)
    title.setAlignment(Qt.AlignmentFlag.AlignHCenter)
    root.addWidget(title)

    row = QHBoxLayout()
    row.setSpacing(8)

    row.addWidget(QLabel("Base endpoint:", screen))
    endpoint = QLineEdit(screen)
    endpoint.setPlaceholderText("https://api.example.com")
    row.addWidget(endpoint, 1)  # stretch: input expands

    root.addLayout(row)

    root.addStretch(1)  # pushes buttons to the bottom

    buttons = QHBoxLayout()
    buttons.addStretch(1)
    buttons.addWidget(QPushButton("Cancel", screen))
    buttons.addWidget(QPushButton("Save", screen))
    root.addLayout(buttons)

    return screen


def main():
    app = QApplication(sys.argv)

    win = QMainWindow()
    win.setWindowTitle("Layout demo")

    win.setCentralWidget(build_screen(win))  # QMainWindow expects a central widget
    win.resize(520, 240)
    win.show()

    sys.exit(app.exec())


if __name__ == "__main__":
    main()

```
<img width="648" height="342" alt="Screenshot 2025-12-29 222459" src="https://github.com/user-attachments/assets/7c7c462e-2d98-4a7a-bba9-f24e35b48deb" />


## Signals

- Signals are like events being fired. For example, when a button is clicked, a right-click, etc.
- Many widgets come with predefined widgets, but you can create more custom signals using pyqtSignal.
- They are initialized like this: `selectSignal = pyqtSignal(object)`. Here _object_ is the type that is going to be emitted.


## More reading material

- [QT6, the underlying framework](https://www.qt.io/)
- https://www.pythonguis.com/pyqt6-tutorial/


