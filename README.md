# FillPDF

FillPDF is a golang library to easily fill PDF forms. This library uses the pdftk utility to fill the PDF forms with fdf data.
Currently this library only supports PDF text and checkbox field values. Feel free to add support to more form types (Send pull request to original developer)
This fork extends with some more pdftk commands - only for the needs I have. 


## Documentation 

Check the Documentation at [GoDoc.org](https://godoc.org/github.com/desertbit/fillpdf).


## Sample

There is an example in the sample directory:

```go
package main

import (
	"log"

	"github.com/desertbit/fillpdf"
)

func main() {
	// Create the form values.
	form := fillpdf.Form{
		"field_1": "Hello",
		"field_2": "World",
	}

	// Fill the form PDF with our values.
	err := fillpdf.Fill(form, "form.pdf", "filled.pdf", true)
	if err != nil {
		log.Fatal(err)
	}
}
```

Run the example as following:

```
cd sample
go build
./sample
```
