# Keyboard Layout Diagrams

Generate printable keyboard layout diagrams for the MoErgo Glove80 keyboard.


## Creating Printable Document

1. Upload JSON files to the [KLE app](https://keyboard-layout-editor.com/#/) and make desired changes. 
2. Save the JSON source file. 
3. Take a screenshot of the layout and save as PNG.
4. Run `rake pdf` to generate `all-layers-diagram.pdf` (and individual layer PDFs)

> TIP: To use Docker, run `./rake pdf` instead.

## Acknowledgements 

- Special thanks to [Sanuku](https://github.com/sunaku/glove80-keymaps)
