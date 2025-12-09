import os
from PIL import Image
from tkinter import Tk, filedialog

def numeric_sort(filename):
    """Extract numeric part before extension for sorting."""
    name, _ = os.path.splitext(filename)
    try:
        return int(name)
    except ValueError:
        return name  # fallback if not numeric

def convert_webp_to_pdf(input_folder, output_folder):
    for root, dirs, files in os.walk(input_folder):
        webp_files = sorted(
            [f for f in files if f.lower().endswith(".jpg")],
            key=numeric_sort
        )
        if not webp_files:
            continue

        folder_name = os.path.basename(root)
        pdf_path = os.path.join(output_folder, f"{folder_name}.pdf")

        print(f"\n📄 Creating PDF: {pdf_path}")
        images = []
        for file in webp_files:
            img_path = os.path.join(root, file)
            try:
                img = Image.open(img_path).convert("RGB")
                images.append(img)
            except Exception as e:
                print(f"❌ Error loading {file}: {e}")

        if images:
            first_img, rest = images[0], images[1:]
            first_img.save(pdf_path, save_all=True, append_images=rest)
            print(f"✅ Saved: {pdf_path}")

def main():
    Tk().withdraw()
    input_folder = filedialog.askdirectory(title="Select Input Folder (with subfolders)")
    if not input_folder:
        print("No input folder selected.")
        return

    output_folder = filedialog.askdirectory(title="Select Output Folder for PDFs")
    if not output_folder:
        print("No output folder selected.")
        return

    convert_webp_to_pdf(input_folder, output_folder)
    print("\n🎉 All done!")

if __name__ == "__main__":
    main()
