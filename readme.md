# Pygame-Click-Manager

`pygame_click_manager` is a Python module designed to facilitate the handling of mouse events and collisions within the Pygame framework. The main class, `ClickManager`, provides methods to check for button clicks, verify if the mouse is within a specified area, and determine if one object is inside or colliding with another object.

## Features

- **Check Button Clicks**: Verify if a button is clicked and execute a command if provided.
- **Mouse Area Check**: Determine if the mouse pointer is within a specified area.
- **Object Containment**: Check if one object is completely inside another object.
- **Object Collision**: Check if one object is colliding with another object.

## Installation

To use `pygame_click_manager`, ensure you have Pygame installed:

```bash
pip install pygame
```

Then, include `pygame_click_manager` in your project by copying the class definition into your codebase.

## Usage

Here's a basic example of how to use the `ClickManager` class:

```python
import pygame
from pygame_click_manager import ClickManager

# Initialize Pygame
pygame.init()

# Create a screen
screen = pygame.display.set_mode((800, 600))

# Define a command to be executed on button click
def button_command():
    print("Button clicked!")

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Check for button clicks
    if ClickManager.check_buttons_for_clicks((100, 100), (150, 50), button_command):
        print("Button area was clicked.")

    # Your game logic here

    # Update the display
    pygame.display.update()

pygame.quit()
```

## Class Reference

### `ClickManager`

#### Methods

- `check_buttons_for_clicks(starting_pos: tuple[int, int], size: tuple[int, int], command=None) -> bool`
  - Checks if a button is clicked within the specified area.
  - **Parameters**:
    - `starting_pos`: The top-left corner of the button area.
    - `size`: The width and height of the button area.
    - `command`: An optional command (function) to be executed when the button is clicked.
  - **Returns**: `True` if the button is clicked, otherwise `False`.

- `_is_mouse_in_area(starting_pos: tuple[int, int], size: tuple[int, int]) -> bool`
  - Checks if the mouse is within a specified area.
  - **Parameters**:
    - `starting_pos`: The top-left corner of the area.
    - `size`: The width and height of the area.
  - **Returns**: `True` if the mouse is in the area, otherwise `False`.

- `is_object_inside_another(start_pos_1: tuple[int, int], size_1: tuple[int, int], start_pos_2: tuple[int, int], size_2: tuple[int, int]) -> bool`
  - Checks if the second object is completely inside the first object.
  - **Parameters**:
    - `start_pos_1`: The top-left corner of the first object.
    - `size_1`: The width and height of the first object.
    - `start_pos_2`: The top-left corner of the second object.
    - `size_2`: The width and height of the second object.
  - **Returns**: `True` if the second object is inside the first object, otherwise `False`.

- `is_object_colliding_with_another(start_pos_1: tuple[int, int], size_1: tuple[int, int], start_pos_2: tuple[int, int], size_2: tuple[int, int]) -> bool`
  - Checks if the second object is colliding with the first object.
  - **Parameters**:
    - `start_pos_1`: The top-left corner of the first object.
    - `size_1`: The width and height of the first object.
    - `start_pos_2`: The top-left corner of the second object.
    - `size_2`: The width and height of the second object.
  - **Returns**: `True` if the objects are colliding, otherwise `False`.

## License

This project is licensed under the MIT License.