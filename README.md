## AirBnB Clone - The console
### Description
This project is the first step towards building an AirBnB clone. The primary goal is to develop a command interpreter to manage AirBnB objects. This command interpreter will serve as the foundation for all subsequent components of the AirBnB web application, including HTML/CSS templating, database storage, API, and front-end integration.

### Command Interpreter
The command interpreter allows users to interact with the AirBnB project through a command-line interface (CLI). It facilitates the management of AirBnB objects such as users, states, cities, and places.

### How to Start
To start the command interpreter, follow these steps:

1. Clone the repository to your local machine: git clone <repository-url>
2. Navigate to the project directory: cd AirBnB_clone
3. Run the command interpreter script: ./console.py

### How to Use
Once the command interpreter is running, you can use it by typing commands followed by any required arguments or options. Here are some common commands and their descriptions:

- create <class_name>: Create a new instance of the specified class.
- show <class_name> <id>: Display the details of a specific instance.
- destroy <class_name> <id>: Delete a specific instance.
- all <class_name>: Display all instances of a specified class.
- update <class_name> <id> <attribute_name> <attribute_value>: Update the attributes of a specific instance.
For a complete list of commands and their usage, refer to the documentation or run the help command within the interpreter.

### Examples

Here are some examples of how to use the command interpreter:

$ ./console.py
#!/usr/bin/python3
"""Module for the entry point of the command interpreter."""

import cmd
from models.base_model import BaseModel
from models import storage
import re
import json


class HBNBCommand(cmd.Cmd):

    """Class for the command interpreter."""

    prompt = "(hbnb) "

    def default(self, line):
        """Catch commands if nothing else matches then."""
        # print("DEF:::", line)
        self._precmd(line)

    def _precmd(self, line):
        """Intercepts commands to test for class.syntax()"""
        # print("PRECMD:::", line)
        match = re.search(r"^(\w*)\.(\w+)(?:\(([^)]*)\))$", line)
        if not match:
            return line

## Authors
* Kathia Karangwa
* Belinda Larose

## Contributing

If you'd like to contribute to this project, please follow these steps:

* Fork the repository.
* Create a new branch for your feature or bug fix.
* Make your changes and commit them to your branch.
* Push to your fork and submit a pull request.
