# Extraction & renommage automatique de photos terrain (OCR + EXIF)

> **🔒 The source code in this repository is encrypted.**
> The archive `photo-ocr-exif-rename.zip` is protected with **WinZip AES-256** encryption.
> The password is shared privately with recruiters / reviewers on request.

## What it does

Pipeline organisant automatiquement des milliers de photos issues d'archives ZIP.

- **Extraction** : lecture du texte sur les photos (EasyOCR) et extraction de l'identifiant (CH IAM, Caniveau) par regex ; lecture des champs EXIF (`UserComment`, `ImageDescription`, `XPComment`).
- **Renommage** : normalisation, gestion des doublons, repli sur le nom d'origine, journal détaillé ancien nom → nouveau nom.

## Results

- Gain de **plusieurs jours** de travail manuel par lot d'archives.
- Nommage homogène et traçable des livrables photo.

## Stack

Python · EasyOCR · Pillow · ExifTags · zipfile · tempfile · shutil · regex

## Decrypt & run

```bash
pip install pyzipper
python3 decrypt.py          # prompts for the password, extracts to ./src
# or without the helper (7-Zip / WinZip / unzip all support AES-256):
7z x photo-ocr-exif-rename.zip -p
```

## Integrity

Every file inside the archive is listed with its SHA-256 in `MANIFEST.sha256`.
Verify **from the repository root** (the paths are relative to it):

```bash
sha256sum -c MANIFEST.sha256      # Linux / macOS / Git Bash
certutil -hashfile src\main.py SHA256   # Windows, per file
```

---
*Ali Nouna — alinouna@gmail.com — linkedin.com/in/AliNouna*
