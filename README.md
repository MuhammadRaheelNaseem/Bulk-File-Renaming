# Bulk File Renaming

This repository provides a Python script to rename multiple PNG files in a directory with a specified prefix followed by an incremented number.

## Table of Contents
1. [Introduction](#introduction)
2. [Script Explanation](#script-explanation)
3. [Usage](#usage)
4. [Customization](#customization)
5. [Contributing](#contributing)
6. [License](#license)

## Introduction

The `rename_files.py` script in this repository allows you to efficiently rename all PNG files within a specified directory. It appends a prefix (`new_xray_`) to each file name followed by an incremented number, ensuring unique names for each file.

## Script Explanation

The script utilizes Python's `os` module for file operations:
```python
import os

def rename_files(folder):
    """
    Renames all PNG files in the given directory with a specified prefix followed by an incremented number.
    
    Parameters:
    folder (str): The path to the directory containing the PNG files.
    
    Returns:
    None
    """
    for count, filename in enumerate(os.listdir(folder)):
        # Construct new file name
        new_filename = f"image_{count + 1}.png"
        
        # Define source and destination paths
        src = os.path.join(folder, filename)
        dst = os.path.join(folder, new_filename)
        
        # Rename the file
        os.rename(src, dst)
        print(f"Renamed: {filename} -> {new_filename}")

if __name__ == '__main__':
	rename_files("path/to/your/png/files")
```

## Usage

To use the script:

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/YOUR_USERNAME/bulk-file-renaming.git
   cd bulk-file-renaming
   ```

2. **Adjust Parameters:**
   - Open `rename_files.py` and modify the `folder` variable to point to your directory containing PNG files.

3. **Run the Script:**
   - Execute the script in your Python environment (`python rename_files.py`).
   - This will rename all PNG files in the specified directory to `new_xray_1.png`, `new_xray_2.png`, etc.

## Customization

You can customize the script:
- **Prefix:** Modify `"new_xray_"` to any prefix you prefer (`"image_"`, `"photo_"`, etc.).
- **File Extension:** Adjust `".png"` to match the file type you are working with (`".jpg"`, `".jpeg"`, etc.).

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or bug fixes, please submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
