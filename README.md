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

### Main Function

1. Reads the `DocumentsFolder` and returns a list of all `docx` files contained therein.
2. Creates the folders needed to store new and processed documents. 
3. Loops through the list of files and calls a function called `ReplaceDocumentWords` for each one. 

### ReplaceDocumentWords Function

1. Extracts the files contained in each `docx` archive into a temporary folder. 
2. Reads the XML file containing the text of the Word Document.
3. Loops through the key-value pairs contained in the `PlaceholderAndValue` list, finds all words matching the value in the placeholder property and replaces them with the value from the `Value` property.
4. Zips the updated files into a new '.docx' file.
5. Saves the new file in the `Results` folder.
6. Moves the processed file to the `Processed` folder. 

## Contributions and questions

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)
