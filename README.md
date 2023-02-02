# Populating a DOCX with placeholder text

## Description
Replacing placeholder text in a `.docx` file

## Prerequisites

1. Linx Designer 6.4.3 or higher

## Usage

To use the sample as-is

1. Download this repo
2. Open the `PopulatePlaceholders.solution` file in the `Linx6` folder
3. Debug the function entitled `Main`
4. Enter the path to the `Template.docx` file in the `example` folder into the parameter entitled `DocumentsFolder`
5. Start the debugger

## Result

1. The text `todays_date` in the document will be replaced by Linx with the current date
2. A new file will be created in a folder called `Results`
3. The original file will be moved to afolder entitled `Processed`

## Customisations

1. Add your own placeholder text to the List entitled `ListOfChanges` in the `Main` function
1. Place any `.docx` files you want processed into the `DocumentsFolder` folder
1. When you debug the `Main` function all `docx` files in that folder will be processed

### How it works

The function called `Main` reads the `DocumentsFolder` and returns a list of all `docx` files contained therein.

It then creates the folders needed to store new and processed documents. 

Finally, it loops through the list of files and calls a function called `ReplaceDocumentWords` for each one. 

The `ReplaceDocumentWords` function first extracts the files contained in each `docx` archive into a temporary folder. 

The XML file containing the text of the Word Document is then read.

The function then loops through the key-value pairs contained in the `PlaceholderAndValue` list, finds all words matching the value in the placeholder property and replaces them with the value from the `Value` property.

When all the replacements have completed, the file contents are overwritten with the new contents.

The files are then zipped back into a '.docx' file.

The new file is then created in the `Results` folder and the processed file is moved to the `Processed` folder.

## Contributing

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)
