# The hacker's notebook (WIP)

Hi! If you are reading this, you are probably trying to understand how this software works internally. **Good for you!**

In general, I try to write [DOXYGEN](https://www.doxygen.nl/index.html) comments to explain what each function does. *However*, this does not help newcomers understand how a program's source code is organized (or how it *works*). For this reason, I will try to explain what each folder & class does in this document. 

Think of this file as an *introductory document* for colaborators, hackers and geeks. Maybe there are superior and more "pure" ways of doing this, but I really like the simplicity of markdown & `git`.

Of course, if this documentation is not clear enough (or you are a good writer), you are very welcome to fork this project, modify it & create a [pull request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

## Software architecture

Before explaining what each module does, please take a look at the "high-level" architecture of Serial Studio. If you have any doubts, feel free to use any of the support channels provided by the maintainers of the project.

![Architecture](/doc/architecture/architecture.svg)

### Source code organization

Since there are over 30 source files that compromise this project (not including any libraries or the [UI/QML](https://github.com/Serial-Studio/Serial-Studio/tree/master/assets/qml) part), it is important to keep the files organized in subdirectories corresponding to the their respective high-level functionalities.

Here is a breakdown of each subdirectory of the source code:

- [`IO`](IO) implements the I/O manager, handlers for device data sources (serial port, network port) & console handler.
    - The I/O manager & console are implemented as [singleton classes](https://en.wikipedia.org/wiki/Singleton_pattern).
- [`MQTT`](MQTT) contains a singleton class that allows Serial Studio to act as an [MQTT](https://en.wikipedia.org/wiki/MQTT) client.

- TODO...

**What about the user interface?** 

The user interface is written in [QtQuick/QML](https://doc.qt.io/qt-5/qtquick-index.html). You can find the "source code" of the user interface in the [`$PROJ_ROOT/assets/qml`](https://github.com/Serial-Studio/Serial-Studio/tree/master/assets/qml) folder.

## Coding styles

If possible, please follow the coding conventions defined in the [`.clang-format`](https://github.com/Serial-Studio/Serial-Studio/blob/master/.clang-format) file. If you are as lazy as me, you can download and install [clang-format-all](https://github.com/eklitzke/clang-format-all) and run the following command before making a commit:

> `clang-format-all src`

This will apply the style defined in the [`.clang-format`](https://github.com/Serial-Studio/Serial-Studio/blob/master/.clang-format) file recursively to all C++ headers and sources in the project. No need to worry about writing "ugly" code anymore!

**IMPORTANT! Please write explanatory comments to document your changes!**




