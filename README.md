# Twistor
Twistor (**Tw**itter **st**ream simulat**or**) is a standardized system to evaluate different event detection algorithms in a consistant way. It simulates the Twitter stream and provides the ability to embed 10 free selectable events into the simulated Twitter stream.

## Requirements
- [Git LFS](https://git-lfs.github.com/) must be installed or `git clone` will not retrieve all needed files (especially base/stream.zip) OR alternatively you can download `base/stream.zip` by hand and place it in `base/`
- JRE 8

## Installation
- Clone the repository
- Adjust the `OUTPUT_DIR` in `src/main/GlobalParameters.java` and set it to a directory in which the file(s) of the simulated Twitter stream are created
- In `src/main/GlobalParameters.java` many other options can be set, they are all commented
- Use the libraries in `libs/` in your Java Build Path and execute `src/main/Stream.java` to create a simulated Twitter stream
