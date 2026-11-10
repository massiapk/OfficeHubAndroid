# Office Hub — Android starter project

Office Hub is a native Android (Kotlin + Jetpack Compose) starter application.

## Included in this first version

- Minimal modern dashboard with dedicated PDF, Word, PowerPoint and Excel colors.
- Import multiple documents using Android's system file picker.
- File-type detection and category filters.
- Search imported files by name.
- PDF page viewer using Android `PdfRenderer`.
- Basic Word-style text editor: title, paragraphs and one embedded image; exports a DOCX file.
- Basic PowerPoint slide builder: add/remove slides, edit slide titles and text; exports a PPTX file.
- Share documents using Android's share sheet.
- Open non-PDF Office files with a compatible app installed on the device.
- GitHub Actions workflow to build a debug APK automatically.

## Important limitation

This is a functional starter version, not a complete Microsoft Office replacement.
Word, Excel and PowerPoint documents are detected and managed inside Office Hub, but their full editing/formatting engines are not embedded yet. The current version hands those formats to a compatible app installed on Android.

For true in-app editing of DOCX, XLSX and PPTX, a document engine must be integrated. Options include a self-hosted ONLYOFFICE Docs or Collabora Online server, or a commercial/mobile SDK. These require additional integration and, for online engines, a server and document conversion/storage endpoints. GitHub Actions builds the APK; it does not provide that document-editing server.

## Build on GitHub (no Android Studio required)

1. Create a new **public or private** repository on GitHub named `OfficeHub`.
2. Extract this ZIP on your phone or computer.
3. Upload the **contents** of the `OfficeHubAndroid` folder to the root of the GitHub repository. Make sure `.github/workflows/build-apk.yml` is included.
4. Open the repository on GitHub and choose **Actions**.
5. Select **Build Office Hub APK** and press **Run workflow**. (A push to `main` also starts a build.)
6. Wait for the green successful result.
7. Open the completed workflow run, find **Artifacts**, and download `OfficeHub-debug-apk`.
8. Extract the downloaded artifact ZIP. Install `app-debug.apk` on your Android phone. If Android asks, allow installation from that source.

## Requirements

- GitHub account.
- Internet connection.
- Android 8.0 or newer for installation (the project minimum is API 26).
- A compatible office application on the phone to edit Word/Excel/PowerPoint in this starter version.

## App identity

- App name: Office Hub
- Application ID: `com.officehub.app`
- Version: `1.0`

## Open-source engine research

For full-fidelity editing of existing DOCX/XLSX/PPTX files, the project can later integrate an office engine. Collabora Online/LibreOffice has a full Writer/Calc/Impress engine but requires a server for its Online variant. The open-source Android app Artefact is another useful reference project (MIT/Apache-2.0) with local Word and spreadsheet editing; check its current source and licence notices before copying or integrating code:
- https://github.com/Chethan616/Artefact
- https://www.collaboraonline.com/
