# Image to PDF Converter (Python)

This Python application converts folders containing **JPG images** into **PDF files**, using automatic sorting and a simple folder-selection interface. Each subfolder is converted into a single PDF with the same folder name.

---

## 📌 Features

- Converts `.jpg` images to PDF
- Automatically sorts images numerically (1.jpg, 2.jpg, 10.jpg…)
- Supports nested folders/subfolders
- Creates one PDF per subfolder
- Simple GUI folder selection using Tkinter
- Handles corrupted or unreadable images gracefully
- Lightweight and runs on Windows, Mac, and Linux

---

## 🛠️ Requirements

Install Python (3.8+ recommended)

Install required library:

```bash
pip install pillow
````

Tkinter comes preinstalled with most Python installations.

---

## 📁 Project Structure

```
project/
│── ItP.py
│── README.md
```

Place any number of subfolders inside the input folder:

```
InputFolder/
│── Chapter1/
│     ├── 1.jpg
│     ├── 2.jpg
│── Chapter2/
      ├── 1.jpg
      ├── 2.jpg
```

Each subfolder becomes:

```
OutputFolder/
│── Chapter1.pdf
│── Chapter2.pdf
```

---

## 🚀 How to Run

Run the script:

```bash
python ItP.py
```

You will be asked to select:

1. **Input Folder** → folder containing subfolders of images
2. **Output Folder** → where generated PDFs will be saved

The program will automatically process everything and display progress in the console.

---

## 🧩 Code Overview

### Numeric Image Sorting

Ensures proper order (1,2,3…10) instead of alphabetic order (1,10,2…).

### PDF Generation

Uses Pillow to convert JPG images to RGB and compile them into a PDF.

### GUI Support

Tkinter’s `filedialog.askdirectory()` is used to select folders easily.

---

## ❗ Troubleshooting

### **ModuleNotFoundError: No module named 'PIL'**

Install pillow:

```bash
python -m pip install pillow
```

### Tkinter not working on Windows

Reinstall Python from:
[https://www.python.org/downloads](https://www.python.org/downloads)
(Do NOT install from Microsoft Store)

### Images not appearing in PDF

Verify images are valid `.jpg` files and not corrupted.

---

## 📜 License

This project is open-source and free to modify.

---

## 🤝 Contributions

Feel free to fork this repository and submit improvements. Suggestions and pull requests are welcome!
