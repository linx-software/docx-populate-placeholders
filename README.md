# Populating a DOCX with placeholder text

## Description
Replacing placeholder text in a `.docx` file

## Prerequisites

1. Linx Designer 6.4.3 or higher

## Usage

1. Download this repo
2. Open the `PopulatePlaceholders.solution` file in the `Linx6` folder
3. Debug the function entitled `Main`
4. Enter the path to the `documents` folder of this repo into the parameter entitled `DocumentsFolder`
5. Start the debugger

## Result

1. The file `Template.docx` in the `documents` folder will be processed and the text `todays_date` will be replaced by Linx with the current date
2. A new file will be created in a folder called `Results`
3. The original file will be moved to a folder entitled `Processed`

## Customisations

1. Add your own placeholder text to the List entitled `ListOfChanges` in the `Main` function
1. Place any `.docx` files you want processed into the `DocumentsFolder` folder
1. Debug the `Main` function. All `docx` files in the `DocumentsFolder` folder will be processed

## Explanation

The function called `Main` reads the `DocumentsFolder` and returns a list of all `docx` files contained therein.

It then creates the folders needed to store new and processed documents. 

Finally, it loops through the list of files and calls a function called `ReplaceDocumentWords` for each one. 

The `ReplaceDocumentWords` function first extracts the files contained in each `docx` archive into a temporary folder. 

The XML file containing the text of the Word Document is then read.

The function then loops through the key-value pairs contained in the `PlaceholderAndValue` list, finds all words matching the value in the placeholder property and replaces them with the value from the `Value` property.

When all the replacements have completed, the extracted and updated files are zipped into a new '.docx' file.

The new file is then saved in the `Results` folder and the processed file is moved to the `Processed` folder.

## Contributions and questions

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)
