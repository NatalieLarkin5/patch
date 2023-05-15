# PATCh

https://sfdl.org.uk/patch

This is a [directory of web applications](https://sfdl.org.uk/patch) built with Python. The apps run entirely in the browser. It uses mainly two libraries:

- [streamlit](https://docs.streamlit.io/) - web applications using simple python code. Check the documentation to learn how to write apps.
- [stlite](https://github.com/whitphx/stlite) - allows to use stramlit in the browser (using pyodide). If you're just writing apps, you don't have to worry about this.

All you need to do is to write your own streamlit apps and they will be accessible from the directory of apps.

# How to start

Let's go ahead and create, run and publish a small testing app. 

> If you just want to see the final result, check [this python file](/apps/001_template/app.py) which creates [this live app](https://share.stlite.net/#url=https://raw.githubusercontent.com/SocialFinanceDigitalLabs/patch/main/apps/001_template/app.py).


## Setup the editor
1. Open the [web-based editor](https://github.com/github/dev) on this repository by pressiong the . key.

2. Ensure you have the suggested extensions installed - a popup should open on the lower right side of your screen a few seconds after you open this editor. If it doesn't, go to the sidebar of the editor, click on the `extensions` icon and check the `recommended` section. You should see a social finance extension called `sf-stlite` (if not, search for it). Install it.

## Create an app
1. Go to the [apps](./apps) directory and create a new directory for your app (for example, `apps/my_very_first_app`) and create your main app python file within it (it can be `apps/my_very_first_app/app.py` or `apps/my_very_first_app/my_very_first_app.py` or whatever you want).

2. Let's create a sample app that asks for a user name and says hello back to the user. In the file `apps/my_very_first_app/app.py` add the following code and save it:

    ```python
    import streamlit as st

    name = st.text_input("What's your name?")

    if name:
        st.write(f'Hello {name}!')
    ```

    In here we:

    - Import the [streamlit](https://docs.streamlit.io/) package
    - ask for the users name with a text input
    - say hello to the user once they submit their name

## Preview the app
1. With your app's python file opened (and focused), click on the `stlite` icon on the sidebar (it should be the one bellow the `github` icon) and press "Launch stlite preview". You can also run it from vscode command palette: `ctrl` + `shift` + `P` and search for the command `launch stlite preview`. You should now see a preview on the right side of your editor, while your app's code is in your left side:

    ![Screenshot of launching previe](/img/preview_sample.gif)

2. You can now edit the code and, once you save the python file, it will update the app's preview accordingly. If it doesn't, edit the settings of your streamlit preview screen (on the top right button) and check the "Run on save" option - that will ensure your preview reloads every time you change something in your code (and save the file(s)).

3. If you need to use external libraries (such as `matplotlib` to render charts or `openpyxl` to read excel files) ensure that those libraries are listed in a `requirements.txt` file in the same directory as your python file is. check [this example for guidance](/apps/002_quality_data_usecase_EH/requirements.txt). 

4. Once you are happy with your changes, you are ready to publish your app (pending on approval) by making a pull request with your new app. Once your code is approved and merged, it will be displayed in the directory of apps in https://sfdl.org.uk/patch.