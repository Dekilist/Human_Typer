# Human Typer

Human Typer is a small Windows desktop app that simulates human-like typing into another application, such as a Google Doc or text editor. It uses a Tkinter control panel for the input text and timing controls, then uses PyAutoGUI to click a target location and type the text with configurable speed, rhythm, pauses, and optional typo correction.

## Features

- Paste or edit the text you want typed.
- Choose typing speed from 10 to 180 WPM.
- Switch between Steady, Natural, and Bursty typing rhythms.
- Add punctuation pauses and random word-break pauses.
- Optionally simulate occasional typos followed by backspace correction.
- Track typed characters, remaining characters, and elapsed time.
- Run from Python or build a standalone Windows `.exe` with PyInstaller.

## Project Files

- `typing_simulator_app.py` - main Tkinter app and typing simulator logic.
- `main.py` - helper script that waits 3 seconds and prints the current mouse position; useful for choosing the click target coordinates.
- `typing_simulator_app.spec` - PyInstaller build configuration.
- `dist/typing_simulator_app.exe` - generated standalone executable, if the build output is present.

## Requirements

- Windows
- Python 3.10 or newer recommended
- PyAutoGUI
- Tkinter, included with most Python installations
- PyInstaller, only needed if you want to rebuild the `.exe`

Install the Python dependencies:

```bash
pip install pyautogui pyinstaller
```

## Run From PyCharm

1. Open the `Human_Typer` project in PyCharm.
2. Make sure the project interpreter has `pyautogui` installed.
3. Run `typing_simulator_app.py`.
4. Paste the text you want typed into the app.
5. Open the document or text field where the text should be typed.
6. Press **Start** in Human Typer.

After pressing **Start**, the app waits briefly, clicks the configured target position, moves the cursor to the end with `Ctrl+End`, and begins typing.

## Set The Click Target

The app currently clicks the coordinates stored in `typing_simulator_app.py`:

```python
self.target_x = 643
self.target_y = 336
```

To find the coordinates for your own screen:

1. Run `main.py`.
2. Move your mouse to the place where Human Typer should click.
3. Wait 3 seconds.
4. Copy the printed position into `self.target_x` and `self.target_y`.

## Build The Executable

From the project folder, run:

```bash
pyinstaller typing_simulator_app.spec
```

The executable will be created at:

```text
dist/typing_simulator_app.exe
```

## Notes

- Keep the target document open and ready before pressing **Start**.
- The app uses real keyboard and mouse automation, so avoid touching the keyboard or changing focus while it is typing.
- To pause the run, click **Stop** in the Human Typer window.
- Use this only where automated typing is appropriate and allowed.
