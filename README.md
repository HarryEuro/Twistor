# Twistor
Twistor (**Tw**itter **st**ream simulat**or**) is a standardized system to evaluate different event detection algorithms in a consistant way. It simulates the Twitter stream and provides the ability to embed 10 free selectable events into the simulated Twitter stream. It was part of my master thesis.

## Requirements
- [Git LFS](https://git-lfs.github.com/) must be installed or `git clone` will not retrieve all needed files (especially `base/stream.zip`) OR alternatively you can download `base/stream.zip` in the repository by hand and place it in your local path in `base/`
- JRE 8

## Installation
- Clone the repository
- Adjust the `OUTPUT_DIR` in `src/main/GlobalParameters.java` and set it to a directory in which the file(s) of the simulated Twitter stream should be created
- In `src/main/GlobalParameters.java` many other options can be set, they are all commented
- Add the libraries in `libs/` to your Java Build Path and execute `src/main/Stream.java` to create a simulated Twitter stream

# Abstract
When evaluating event detection algorithms two problems can occur. The first problem is that Twitter's terms and conditions prohibit the exchange of Twitter data. So every researcher has to collect his own data and the evaluation of his event detection algorithm is based on individually collected data which can vary in quality and consistency. The second problem is that when applying an event detection algorithm on the Twitter stream it is not known which events are actually in the stream. So the validation of the event detection results is a big challenge and often solved individually by every researcher on his own. So evaluations from different researchers are often not comparable. Twistor (**Tw**itter **st**ream simulat**or**) solves both of these problems.

Twistor simulates the Twitter stream and provides the ability to embed 10 free selectable events into the simulated Twitter stream. With Twistor every researcher can create Twitter stream data which has the same quality and consistency. Also it is exactly known which events are embedded in the artificial stream and therefore which events should be recognized by an event detection algorithm. So Twistor can be used as a standardized system to evaluate different event detection algorithms in a consistant way. 

Twistor itself consists of two components. The first component is the simulation of the Twitter stream and the second one is the integration of events into the simulated Twitter stream.

To create a precise representation of the original Twitter stream the simulated Twitter stream is based on original Twitter data (collected with the garden hose access which reprents 10 % of the original Twitter stream). Over a time period of 24 hours the term distribution in the original Twitter data is captured in one minute windows. The distribution of the terms is saved for every window in an external file (basis information). The basis information is created only once. Using the basis information Twistor produces the simulated stream. Since the distribution of the terms is quantified in the basis information the simulated stream can also be scaled up to 100 % (based on the 10 % garden hose access). So a simulation of a fire hose access is also possible.

That the 10 free selectable events which can be integrated into the simulated Twitter stream reflect an event in Twitter as accurate as possible the events are also based on original Twitter data. An event itself is represented by atleast of two words. The IDF values of the words representing the event are captured with a sample rate of one second at the time the event happend and saved in a file. To embed an event into the simulated Twitter stream the IDF values of the words representing the event are mapped into it. To map the IDF values of a word into the artifical Twitter stream the amount of tweets per second which should contain the word is computed and the word is inserted into the simulated tweets.
