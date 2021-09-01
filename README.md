# Pakistani-cars-Number-Plate-Recognition-using-Pytesseract-in-Python

## Perspective De-skewing Through Contours

•	Image enhancement [resizing, grayscale, gaussian blur, adaptive thresholding]
•	Contour detection
•	Contour sorting (left-to-right)
•	Height and width thresholding
•	Finding unique contours from the list of contours
•	Finding coordinates of each contour
•	Extracting left top’s and right bottom’s of all contours for manipulation
•	Slicing first left and last bottom to get corner coordinates  
•	Adding and subtracting some pixels out of corner coordinates to introduce slight skewness for perspective transform.
•	Application of perspective transform on enhanced and skewed images

## Pytesseract after Image Enhancement Techniques

•	Image enhancement [resizing, gaussian blur, Otsu’s thresholding, 2D-sharpening]
•	Passing enhanced image to pytesseract for text extraction
•	Appending text in a list for post processing
•	Frequency Matching of maximum entries and accessing the top entry
•	Checking the length of the extracted text

o	If length is less than 7, we slice the first half chunks for alphabets and remaining half as numbers. 
	Check if the length is divisible by 2, slice the first half as alphabets and second half as numbers.
	Else, increment the length and do the same as above except this time subtract one to get three numbers. (e.g if length is 5, chances are that the text will have three alphabets and two numbers. So, it will slice first three and last three)  
o	Else, we check the criteria through regular expression for both Alphabets and numbers.
	Check if the length is divisible by 2, slice the first half as alphabets and second half as numbers
	Else, increment the length and do the same as above except this time subtract one to get three numbers. (e.g if length is 7, chances are that the text will have three alphabets and four numbers. So, it will slice first three and last four).  
o	Make a list comprehension for alphabets to numbers conversion having similar features (e.g A to 4, B TO 8, d to 0 etc). 
o	Make another list comprehension for numbers to alphabets conversion having similar features (e.g 4 to A, 8 TO B, so forth). 
o	After conversion, we join the two lists by removing the spaces for forming a single word. 
