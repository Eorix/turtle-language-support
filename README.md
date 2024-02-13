# Turtle Language Support Extension for Visual Studio Code

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://en.wikipedia.org/wiki/Software_versioning)
[![Repository](https://img.shields.io/badge/Repo-100000?&logo=github&logoColor=white)](https://github.com/Eorix/turtle-language-support)
[![Visual_Studio_Code](https://img.shields.io/badge/Visual_Studio_Code-0078D4?logo=visual%20studio%20code&logoColor=white)](https://code.visualstudio.com/)
[![Windows](https://img.shields.io/badge/Windows-0078D6?&logo=windows&logoColor=white)](https://en.wikipedia.org/wiki/Microsoft_Windows)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?logo=ubuntu&logoColor=white)](https://en.wikipedia.org/wiki/Ubuntu)

---

This extension enriches Visual Studio Code with syntax highlighting capabilities tailored for the Turtle language, enhancing your development experience.

## Features

- **Syntax Highlighting**: Enjoy syntax highlighting for `.turtle` files, making code easier to read and understand.

## Installation

You can easily install the extension by importing the `.vsix` package into your Visual Studio Code editor.

## Usage

Once installed, simply open a `.turtle` file in Visual Studio Code, and the syntax highlighting will be automatically applied, helping you to focus on your project.

## Contributing

Contributions to this extension are welcome and straightforward. You'll find the grammar definition in the "syntaxes/turtle.tmLanguage.json" file. This file utilizes regular expressions to match tokens recognized by Visual Studio Code. Understanding how syntax highlighting works in VS Code involves recognizing that it uses TextMate under the hood to match grammars to predefined tokens. These tokens are then mapped to the current global editor theme, ensuring automatic highlighting. This extension follows this pattern and maps different regexes to various predefined tokens in the "turtle.tmLanguage.json" file. You can refer to the [TextMate language grammars manual](https://macromates.com/manual/en/language_grammars) (section 12.4) for a non-exhaustive list of these tokens.

As an example, let's define some keywords for Turtle:

```json
{
    "name": "keyword.control.turtle",
    "match": "\\b(color|repeat|proc|call|set|quit|exit)\\b"
}
```

Here, "name" references the predefined token. In this case, we define `(color|repeat|...|exit)` as control keywords, which will be highlighted similarly to keywords like `while`, `break`, `continue`, etc., available in the C language, as they use the same token.

Finally, "match" is where the regex is defined.

## Building

To build the `.vsix` package for this extension, follow these steps:

1. **Install `vsce`**: First, ensure you have the `vsce` module installed in npm. You can install it globally using npm by running:
   ```bash
   npm install -g vsce
   ```

2. **Execute Command**: Once `vsce` is installed, navigate to the root of the extension folder in your terminal. Then, execute the following command:
   ```bash
   vsce package
   ```

   This command generates a `.vsix` package, typically named `turtle-language-support-1.0.0.vsix`.

3. **Import Package**: After packaging, you can import the generated `.vsix` package into Visual Studio Code by following these steps:
   - Open the extensions menu in Visual Studio Code (usually found on the left sidebar).
   - Click on the three dots button in the top right corner of the extensions menu.
   - Choose `Install from VSIX...` from the dropdown menu.
   - Select the generated `.vsix` package (`turtle-language-support-1.0.0.vsix`) from your file system and install it.

By following these steps, you should be able to build and install the extension into your Visual Studio Code editor.

## License

This extension is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/), ensuring freedom to use and contribute.