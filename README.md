# neatly file organizer

**Tidy any folder in one click.** Neatly is a lightweight Python tool that sorts the files in a folder into clean, categorized subfolders. Pick a folder, and it does the rest.

**Author:** [Sayed Jibril](https://github.com/Sayed-jibril)

---

## How It Works

1. **Pick a folder:** a native folder picker opens so you can choose any directory
2. **Scan:** Neatly finds every file in that folder (subfolders are ignored)
3. **Organize:** it creates an `Organized_Files` folder with a subfolder for each category
4. **Move:** each file goes into the category that matches its type
5. **Resolve duplicates:** name clashes are renamed automatically (e.g. `file(1).pdf`)
6. **Summarize:** a final report shows what was moved

## Categories

| Category       | File types                   |
| -------------- | ---------------------------- |
| **PDFs**       | `.pdf`                       |
| **Images**     | `.jpg` `.jpeg` `.png` `.gif` |
| **Excel**      | `.xls` `.xlsx`               |
| **Word**       | `.doc` `.docx`               |
| **PowerPoint** | `.ppt` `.pptx`               |
| **Text**       | `.txt`                       |
| **Others**     | everything else              |

## Getting Started

### Prerequisites

- Python 3.6 or higher
- tkinter (included with most Python installations)

### Installation

```bash
git clone https://github.com/Sayed-jibril/neatly-file-organizer.git
cd neatly-file-organizer
```

### Run

```bash
python file_organizer_bot.py
```

You can also double-click `file_organizer_bot.py`.

Then:

1. Choose the folder you want to organize in the dialog
2. Wait a moment while the files are sorted
3. Read the summary, and confirm in the success dialog

## Example

**Before**

```
Downloads/
├── document.pdf
├── photo.jpg
├── spreadsheet.xlsx
├── presentation.pptx
├── notes.txt
└── music.mp3
```

**After**

```
Downloads/
└── Organized_Files/
    ├── PDFs/
    │   └── document.pdf
    ├── Images/
    │   └── photo.jpg
    ├── Excel/
    │   └── spreadsheet.xlsx
    ├── PowerPoint/
    │   └── presentation.pptx
    ├── Text/
    │   └── notes.txt
    └── Others/
        └── music.mp3
```

## Safety

- **Nothing is deleted:** files are only moved, never removed
- **Self-protection:** the script leaves itself alone and won't organize its own file
- **Top level only:** only files in the root of the chosen folder are processed; existing subfolders are untouched
- **Duplicates are safe:** files with the same name are numbered instead of overwritten
- **Write access required:** you need permission to modify the folder you select

## Customization

To add a category, edit the `categories` dictionary in the `FileOrganizerBot` class:

```python
self.categories = {
    'PDFs': ['.pdf'],
    'Images': ['.jpg', '.jpeg', '.png', '.gif'],
    # Add your own
    'Videos': ['.mp4', '.avi', '.mkv'],
    # ... other categories
}
```

## Testing

```bash
python test_organizer.py
```

This creates sample files and runs the full organization process to verify everything works.

## Troubleshooting

**"tkinter not available"**
Use a Python distribution that includes tkinter. On Debian/Ubuntu, install it with `sudo apt install python3-tk`.

**"Permission denied"**
Make sure you have write access to the target folder. If it's a protected location, run the script with elevated permissions (administrator on Windows, `sudo` on macOS/Linux).

**The script doesn't start**
Confirm Python 3.6+ is installed, then run it from the command line (`python file_organizer_bot.py`) to see any error messages.

## Contributing

Ideas and improvements are welcome. Fork the repo, create a branch, and open a pull request.

## Author

**Sayed Jibril**: [github.com/Sayed-jibril](https://github.com/Sayed-jibril)

---

**Neatly**: less clutter, more focus.
