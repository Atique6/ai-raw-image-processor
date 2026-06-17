# AI RAW Image Processor

AI RAW Image Processor is a desktop application that helps users edit RAW photos using manual controls and AI-powered suggestions.

The app lets users import RAW image files, adjust parameters such as exposure and contrast, preview edits, compare original and edited versions, and export the final image.

---

## Features

* Import RAW image files such as `.DNG` and `.CR3`
* Adjust exposure, contrast, highlights, shadows, and black levels
* Get AI-powered editing suggestions using Gemini
* Preview image changes inside the app
* Compare original and edited versions
* Export edited images
* Store image paths and adjustment settings locally with SQLite
* Includes unit tests for core application logic

---

## Tech Stack

| Tool       | Purpose                                       |
| ---------- | --------------------------------------------- |
| Python     | Main programming language                     |
| Flet       | Desktop app interface                         |
| SQLite     | Local image library and saved adjustment data |
| rawpy      | RAW image processing                          |
| Pillow     | Image conversion and saving                   |
| OpenCV     | Image processing support                      |
| Gemini API | AI editing recommendations                    |
| pytest     | Testing                                       |

---

## Project Structure

```text
ai-raw-image-processor/
├── README.md
├── .gitignore
├── .env.example
├── requirements.txt
├── pyproject.toml
├── imageprocessor/
│   ├── main.py
│   ├── ImageProcessing.py
│   ├── ai_integration.py
│   ├── config.py
│   ├── data.py
│   └── directory_management.py
├── sample_images/
│   ├── PAN00001.DNG
│   ├── R62_0323.CR3
│   └── R62_4289.CR3
└── tests/
    ├── test_ImageProcessing.py
    ├── test_api.py
    ├── test_database.py
    ├── test_directory_managment.py
    └── test_main.py
```

---

## How It Works

```text
User imports RAW image
        ↓
App loads and processes the image
        ↓
User adjusts sliders or enters an editing prompt
        ↓
Gemini suggests editing improvements
        ↓
App applies image adjustments
        ↓
User previews, compares, and exports the final image
```

---

## Setup Instructions

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Create a `.env` file

Create a file named `.env` in the main project folder.

Add your Google AI Studio API key:

```text
GOOGLE_AI_STUDIO_API_KEY=your_api_key_here
```

Do not upload your `.env` file to GitHub.

### 3. Run the app

From the main project folder, run:

```bash
cd imageprocessor
python main.py
```

or:

```bash
cd imageprocessor
flet run main.py
```

---

## Running Tests

From the main project folder, run:

```bash
pytest
```

---

## Sample Images

The `sample_images/` folder contains RAW images used to test importing, editing, previewing, and exporting.

---

## Main Files

| File                      | Purpose                                    |
| ------------------------- | ------------------------------------------ |
| `main.py`                 | Main application and user interface        |
| `ImageProcessing.py`      | RAW image rendering and adjustment logic   |
| `ai_integration.py`       | Sends image data and prompts to Gemini     |
| `data.py`                 | SQLite database operations                 |
| `directory_management.py` | Manages app storage folders                |
| `config.py`               | App settings and supported file extensions |

---

## Future Changes

* Package the app for macOS and Windows
* Add batch image processing
* Add more editing controls such as saturation and temperature
* Improve before and after preview layout
* Add stronger error handling for unsupported image files

