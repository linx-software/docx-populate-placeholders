# Populating a DOCX with placeholder text

## Overview

The provided sample achieves the task of replacing placeholder text within a `.docx` file.

---

### Additional resources

- [Linx community article](https://community.linx.software/community/t/populating-a-word-document/400)

---

## Dependencies

### Pre-requisites

- Linx Designer

### Linx Designer

This solution was developed in the Linx Designer `v5.20.2.0`

---

## Setting up the sample

Configure the Solution's $.Settings:

1. Open the [sample Solution](Solution.lsoz) in your Linx Designer.
1. Edit the $.Settings values:

   - `RootFolder`: The root folder used to process the files. Default it `C:\Linx\PopulatingWordDocument\`

1. Save the Solution.

---

## Using the sample

To use the sample as-is, download the [template document](Template.docx) , place it in the `C:\Linx\PopulatingWordDocument\Inbox\` folder.

Run the `ReplacePlaceholdersInFiles` function.

The text `todays_date` will be replaced by Linx with the current date in a readable format.

The new file will be located at `C:\Linx\PopulatingWordDocument\Results\Template_1.docx` .

### ReplacePlaceholdersInFiles

1. Add your placeholder text and replacement value to the `ListOfChanges`.
1. Place your `.docx` file in the inbox location.
1. Debug the function.
1. Your populated word document will then be available in the results folder.

---

### PopulateWordDocument

This function recieves a list of key-value pairs which contain a placeholder to match and a replacement value and a `.docx` file path.

The function starts by generating a temporary folder name and then unzipping the `.docx` file into this temporary folder.

The XML file containing the text of the Word Document is then read.

For each key-value pair in the list, the contents are the file are searched for a matching placeholder value and then replaced with the value of the key-value pair.

When all the replacements have completed, the file contents are overwritten with the new contents.

The files are then zipped back into a '.docx' file.

The new file is then moved to the 'results' location.
