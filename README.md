# Viewing Party

## Learning Goals

- nested loops
- nested data structures
- logic
- working with lists

## Goal

You and your friends enjoy watching things together online. Of course, everyone has seen different things, has different favorites, and different things they want to watch.

You've been using a spreadsheet to compare everyone's watched list, favorites list, and watchlist, but it's been getting too cumbersome. In order to find things you've watched and your friends haven't watched, or things that your friends have watched and yo haven't watched, you have to comb through the spreadsheet. You know that there are different ways we can get that information: we can use Python!

For this project, given some data structure that represents the things you've watched, favorited, and want to watch, follow the directions below. The directions will lead you to create a series of functions. These functions will modify the data so you can add and remove things from your lists. Also, many of them will create recommendations, based on different information available!

## One-Time Project Setup

Follow these directions once, a the beginning of your project:

1. Navigate to your projects folder named `projects`

```
$ cd ~/Developer/projects
```

2. "Clone" (download a copy of this project) into your projects folder. This command makes a new folder called `viewing-party`, and then puts the project into this new folder.

```
$ git clone ...
```

Use `ls` to confirm there's a new project folder

3. Move your location into this project folder

```
$ cd viewing-party
```

4. Create a virtual environment named `venv` for this project:

```
$ python3 -m venv venv
```

5. Activate this environment:

```
$ source venv/bin/activate
```

6. Install dependencies once at the beginning of this project with

```
$ python3 -m pip install -r requirements.txt
```

Learn markdown checklist:
- [] `cd` into your `projects` folder
- [] Clone the project onto your machine
- [] `cd` into the `viewing-party` folder
- [] Create the virtual environment `venv`
- [] Activate the virtual environment `venv`
- [] Install the dependences with `pip`

## Project Development Workflow

1. When you want to begin work on this project, ensure that your virtual environment is activated:

```
$ source venv/bin/activate
```

2. Find the test file that contains the tests you want to run. Ensure that the tests in the file isn't skipped.

    - Check the `tests` folder, and find the test file you want to run
    - In that test file, read through each test case
    - Remove all lines that contain `@pytest.mark.skip()`

3. Run the tests!

```
$ python3 -m pytest
```

Callout: Why is the command `python3 -m pytest`? The `python3 -m` command says "execute what's to the right, and include the current project." In general, the pytest package needs to be able to discover our tests and our source code. Therefore, `python3 -m pytest` runs the `pytest` command, and ensures that our tests and source code are discoverable.

4. Focus on the top test failure. Read through the test failure, and understand why the failure is happening. Confirm your findings with a classmate.

5. Make a plan to fix the test failure.

6. Write code to fix the test failure.

7. Re-run the tests.

8. Repeat steps 5-7 until that test passes!

9. Repeats steps 4-8 until you have finished all tests in the file.

10. Begin using the test file of the next wave!

11. When you are finished working for the day, deactivate your environment with

```
$ deactivate
```

Callout: Alternatively, you could close this Terminal tab/window.

## Details About How to Run Tests

Run all unskipped tests that exist in this project with:

```
python3 -m pytest
```

If you want to see any `print` statements print to the console, add `-s` to the end of any `pytest` command:

```
python3 -m pytest -s
```

If you want to run all unskipped tests that exist in one file, use:

```
$ python3 -m pytest tests/test_file_name.py
```

... where `test_file_name.py` is relpaced with the correct test file name.

## Project Write-Up: How to Complete and Submit

The goal of this project is to write code in `main.py` so that as many of the tests pass as possible.

To complete this project, use the above workflow and follow these steps:

1. Start with making the tests in `test_wave_one.py` pass.
1. Review your code in `main.py` and see if there are ways you can make the code more readable.
1. Then, work on making the tests in `test_wave_two.py` pass.
1. Review your code in `main.py`
1. Then, work on making the tests in `test_wave_three.py` pass.
1. Review your code in `main.py`

At submission time, no matter where you are, submit the project via ...

## Project Directions

This project is designed such that one could puzzle together how to implement this project without many directions.

Being able to use tests to drive project completion is a skill that needs to be developed; programmers often take years to develop this skill competently.

When our test failures leave us confused and stuck, let's use the detailed project requirements below.

### Wave 1

1. The first four tests are about a `create_movie()` function.

In `main.py`, there should be a function named `create_movie`. This function should...
  - take there parameters: `title`, `genre`, `rating`
  - If those there attributes are truthy, then return a dictionary. This dictionary should...
      - Have three key-value pairs, with specific keys
      - The three keys should be `"title"`, `"genre"`, and `"rating"`
      - The values of these key-value pairs should be appropriate values
  - If `title` is falsy, `genre` is falsy, or `rating` is falsy, this function should return `None`

2. The next test is about a `add_to_watched()` function.

In `main.py`, there should be a function named `add_to_watched`. This function should...
  - take two parameters: `user_data`, `movie`
    - the value of `user_data` will be a dictionary with a key `"watched"`, and a value `[]`
        - This represents that the user has no movies in their watched list
    - the value of `movie` will be a dictionary in this format:
        - ```python
          {
            "title": "Title A",
            "genre": "Horror",
            "rating": 3.5
          }
          ```
  - add the `movie` to the `"watched"` list inside of `user_data`
  - return the `user_data`

3. The next test is about a `add_to_watchlist()` function.

In `main.py`, there should be a function named `add_to_watchlist`. This function should...
  - take two parameters: `user_data`, `movie`
    - the value of `user_data` will be a dictionary with a key `"watchlist"`, and a value `[]`
        - This represents that the user has no movies in their watchlist
    - the value of `movie` will be a dictionary in this format:
        - ```python
          {
            "title": "Title A",
            "genre": "Horror",
            "rating": 3.5
          }
          ```
  - add the `movie` to the `"watchlist"` list inside of `user_data`
  - return the `user_data`

4. There are three tests about a `watch_movie()` function.

In `main.py`, there should be a function named `watch_movie`. This function should...
  - take two parameters: `user_data`, `title`
    - the value of `user_data` will be a dictionary with a `"watchlist"` and a `"watched"`
        - This represents that the user has a watchlist and a list of watched movies
    - the value of `title` will be a string
        - This represents the title of the movie the user has watched
  - If the title is in a movie in the user's watchlist:
    - remove that movie from the watchlist
    - add that movie to watched
    - return the `user_data`
  - If the title is not a movie in the user's watchlist:
    - return the `user_data`



```
{
  watchlist:[]
  favorites:[]
  watched:[]
  friends: {
    watched:[]
    }
}
```

Creates a data structure from input:
Given some fields, creates a movie dict
Given some user data, adds a movie to the watched list
Given some user data, adds a movie to the watchlist

move a movie from watchlist to watched


One loop:
What is the average rating of the movies I've watched
What is the most common genre of the movies I've watched

Nested loops:
Between my friends, what is the average rating of the movies they've watched
Most common genre of movies my friends have watched

Nested loops + Compare with me (could be another loop):
What are all the movies I've seen that they haven't seen
What are all the movies they've seen that I haven't seen
What are all the movies they've seen that I haven't seen on a streaming service that I have

Intense logic that can rely on previous functions if useful, probably the most optional?:
Pick a movie for me; it should match my most common genre, a movie i haven't seen, but one of my friends has
Pick a movie for me; it should be in my favorites, and my friends haven't seen it
