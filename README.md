# BPMN to SVG Automation

This repository automates the conversion of BPMN (Business Process Model and Notation) files to SVG (Scalable Vector Graphics) using GitHub Actions. Whenever you add new BPMN files to the designated folder, the workflow generates corresponding SVGs, keeps track of processed files, and organizes them neatly within the repository.

## How It Works

1. **Add BPMN Files:**
   - Place your `.bpmn` files in the `bpmn-files/` directory.

2. **Automatic Conversion:**
   - On every push or pull request to the `main` branch, the GitHub Actions workflow scans for new BPMN files.
   - It converts each unprocessed BPMN file to an SVG using the [Kroki API](https://kroki.io/).
   - Generated SVGs are saved in the `svg-files/` directory.
   - Processed BPMN files are moved to the `bpmn-files-processed/` directory.
   - The `processed.txt` file logs all processed BPMN files to avoid duplicate processing.

3. **Commit and Push:**
   - The workflow commits the new SVGs, updates `processed.txt`, and pushes the changes back to the `main` branch automatically.