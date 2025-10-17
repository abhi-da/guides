## Advantages Over Overleaf

- ✅ **Offline Access** - No internet required
- ✅ **Faster Compilation** - Local processing
- ✅ **Complete Customization** - Full control over environment
- ✅ **Better Performance** - Handles large documents efficiently
- ✅ **Enhanced Privacy** - Documents stay on your machine
- ✅ **Cost Effective** - No subscription fees
- ✅ **Local file system access - Images stay on your computer**
- ✅ **Direct referencing - Use relative paths in your LaTeX code**
- ✅ **No uploading required - Images are accessed directly from your project folder**



# VS Code LaTeX Setup Guide

A complete guide to setting up VS Code for LaTeX editing with local compilation.


### Step 1: Install LaTeX Distribution

#### macOS Users
- **Download**: [MiKTeX for macOS](https://miktex.org/download/ctan/systems/win32/miktex/setup/darwin-x86_64/miktex-22.1-darwin-x86_64.dmg)
- **Installation Guide**: [MiKTeX macOS Tutorial](https://miktex.org/howto/install-miktex-mac)

#### Windows Users
- **Download**: [MiKTeX for Windows](https://miktex.org/download/ctan/systems/win32/miktex/setup/windows-x64/basic-miktex-24.1-x64.exe)
- **Installation Guide**: [MiKTeX Windows Tutorial](https://miktex.org/howto/install-miktex)

> **Important for Windows**: During installation, select **"Install MiKTeX for everyone"** to automatically add it to your system PATH.

### Step 2: Verify Installation

#### Windows Verification
Open Command Prompt and run:
```cmd
pdflatex --version
latex --version
```

#### macOS Verification
Open Terminal and run:
```bash
pdflatex --version
latex --version
which pdflatex
```

If these commands return version information, LaTeX is properly installed and configured.

### Step 3: Install VS Code

Download and install VS Code from the official website:
- **Download**: [Visual Studio Code](https://code.visualstudio.com/download)

## VS Code Configuration

### Step 4: Install Required Extensions

Open VS Code and install these essential extensions:

1. Press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac) to open Extensions
2. Search for and install:
   - **LaTeX Workshop** by James Yu
   - **LaTeX Utilities**
   - **Spell Right**
   - **LaTeX Snippets**
   - **LaTeX Formatter**
   - **Prettier**

### Step 5: Configure VS Code Settings

1. Open Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
2. Type: `Preferences: Open Settings (JSON)`
3. Add the following configuration:

```json
{
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex ➞ bibtex ➞ pdflatex × 2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.autoBuild.run": "onSave"
}
```

## Usage

### Creating Your First LaTeX Document

1. Open a folder in VS Code
2. Create a new file called `main.tex`or any other filename with extension .tex
3. Add basic LaTeX content:
```latex
\documentclass{article}
\begin{document}
latex is working fine.
\end{document}
```
4. Save the file - it will automatically compile
5. View the PDF in the integrated tab

## Advanced Features

### Version Control with Git
- Track changes in your LaTeX documents
- Collaborate using GitHub/GitLab
- Maintain complete version history

### Multi-Language Integration
VS Code enables seamless integration with:
- **Python** for data analysis and plotting
- **R** for statistical analysis
- Any programming language alongside LaTeX


## Troubleshooting

### Common Issues

1. **LaTeX commands not found**
   - Restart VS Code after LaTeX installation
   - Verify PATH configuration

2. **Compilation errors**
   - Check LaTeX Workshop output panel
   - Ensure all required packages are installed

3. **PDF not updating**
   - Clean auxiliary files using the brush icon
   - Rebuild the document manually

## Support

For issues with:
- **LaTeX Installation**: Refer to MiKTeX documentation
- **VS Code Configuration**: Check LaTeX Workshop GitHub repository
- **Extension Issues**: Visit respective extension pages

---


