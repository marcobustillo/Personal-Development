# Concatenation
**Concatenation** joins text items together.

## Usage
### Simple Concatenate
=CONCATENATE(text1,text2,text3)
="sampletext"&"sampletext2"

### Concatenate with line breaks
=A1 & "/" & B1
=CONCATENATE(A1, "/", B1)

## Arguments
text- text value you need to join

## CONCATENATE vs &
The only essential difference between CONCATENATE and "&" operator is the 255 strings limit of the Excel CONCATENATE function and no such limitations when using the ampersand.

## Return value
Text joined together.
