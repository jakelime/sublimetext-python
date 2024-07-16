# How to configure SublimeText to run python

By default, `CTRL-B` will build the source using `python` (built-in into SublimeText) to run.
Output will be piped to another window in the app.

## MacOS

1. Select Tools >> New build system in sublime text. This will open a new build system config file. In that file delete everything and paste this:

   ```json
    {
        "cmd": ["/Users/jakelim/miniconda3/bin/python","-u", "$file"],
        "selector": "source.python",
        "file_regex": "^\\s*File \"(...*?)\", line ([0-9]*)"
    }
   ```

1. To work out the path to the desired python interpreter:

   1. in the terminal, go to your project directory, make sure it is `venv` is activated, then `which python3` command

1. Save the file and then run your program with the new build system. It will appear in the build system tab in tools.

## Sources

- [Stackoverflow - 64580984](https://stackoverflow.com/questions/64580984/how-to-use-sublimetext-within-a-venv)
