# GPhotos Metadata Fixer - Documentation

View online at:
# [https://gphotos.andersdn.com](https://gphotos.andersdn.com)

My gPhotos Metadata Fixer is a privacy-first, browser-based tool designed to solve the "Google Takeout Problem." 

When you export your photos from Google Photos, the metadata (dates, GPS, descriptions) is often stripped from the image files and placed into separate `.json` "sidecar" files. This tool merges that data back into your images.

## What it does
The tool scans your Google Takeout export (either as a `.zip` file or an extracted folder), matches each image with its corresponding `.json` metadata file, and embeds the information directly into the image's EXIF data.

> It does not modify your original files, but instead creates a new folder with the fixed files. 

> Presently, **Only images are supported**, and only JPEG and HEIC files are processed.

### Merged Metadata
The following information is extracted from the Google JSON files and embedded into your photos:
- **Date & Time**: Sets `DateTimeOriginal`, `CreateDate`, and `ModifyDate` based on the "Photo Taken Time."
- **GPS Location**: Restores Latitude, Longitude, and Altitude.
- **Descriptions**: Maps Google's "Description" or "Title" fields to `ImageDescription`, `Title`, and `XPComment`.
- **People & Keywords**: Converts tagged people into `Keywords` and `Subject` tags.
- **HEIC Conversion**: Automatically converts `.heic` files to `.jpg` to ensure compatibility and metadata embedding.

## How to use
1. **Export from Google Takeout**:
   - Go to [takeout.google.com](https://takeout.google.com/).
   - Select only **Google Photos**.
   - Choose specific albums to keep the export size manageable.
   - Download the resulting `.zip` file.
2. **Select Source**: In the app, click the folder or zip icon to select your Takeout export.
3. **Select Target**: Select an **empty folder** on your computer where the fixed photos will be saved.
4. **Process**: Check the disclaimer and click **Start Processing**.

## Privacy & Security
- **100% Local**: All processing happens inside your browser using WebAssembly (WASM).
- **No Uploads**: Your photos never leave your computer.

## Support & Updates
This is a **side project** created out of necessity. 
- **Infrequent Updates**: Updates will be infrequent and based on personal availability.
- **Issues**: If you encounter a bug or have a suggestion, please [submit an issue on GitHub](https://github.com/andersdn/GPhotos-Metadata-Fixer-Documentation/issues). While I cannot guarantee a fix, I will review flagged issues when possible.

---
*Disclaimer: This tool is not affiliated with, sponsored by, or endorsed by Google LLC.*
