# NLHDH Research Report

This project is a LaTeX report exported from Overleaf. It is configured for local editing in VS Code with MiKTeX Basic, LaTeX Workshop, and XeLaTeX.

XeLaTeX is used because the report contains Vietnamese text and uses Unicode fonts such as Times New Roman. This project does not use `latexmk`, does not require Perl, and does not require TeX Live Full.

## Install

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Install the VS Code extension [LaTeX Workshop](https://marketplace.visualstudio.com/itemdetails?itemName=James-Yu.latex-workshop).
3. Install [MiKTeX Basic](https://miktex.org/download).
4. Open **MiKTeX Console**.
5. Go to **Settings** and enable missing package installation on-the-fly. The easiest option is usually **Always install missing packages on-the-fly**.
6. In MiKTeX Console, check for updates and install them if prompted.

MiKTeX documentation for automatic package installation is available here: [Automatic Package Installation](https://docs.miktex.org/manual/autoinstall.html).

## Add MiKTeX To PATH

VS Code must be able to find `xelatex.exe`. If building fails with `spawn xelatex ENOENT` or `xelatex is not recognized`, add the MiKTeX `bin\x64` folder to your Windows user `Path`.

Typical user install path:

```text
C:\Users\<your-user-name>\AppData\Local\Programs\MiKTeX\miktex\bin\x64
```

Example:

```text
C:\Users\hiinn\AppData\Local\Programs\MiKTeX\miktex\bin\x64
```

If MiKTeX was installed for all users, the path may be:

```text
C:\Program Files\MiKTeX\miktex\bin\x64
```

After changing `Path`, fully close VS Code and reopen it. Then open a VS Code terminal and check:

```powershell
where xelatex
xelatex --version
```

If both commands work, LaTeX Workshop can find XeLaTeX.

## Build The Report

1. Open this folder in VS Code.
2. Open `main.tex`.
3. Build with `Ctrl + Alt + B`.
4. Open the PDF preview with `Ctrl + Alt + V`.

The PDF and build files are written to the `build/` folder. The LaTeX Workshop settings are stored in `.vscode/settings.json` so collaborators can use the same XeLaTeX setup.

## Notes

- Keep `main.tex` as the main/root file.
- Use XeLaTeX for this project, not pdfLaTeX.
- Do not switch the recipe to `latexmk`; this setup intentionally avoids Perl.
- On the first build, MiKTeX may install several missing packages. Let it finish, then build again if needed.
