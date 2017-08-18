 
 
 [![Build Status](https://travis-ci.org/hhrutter/pdflib.svg?branch=master)](https://travis-ci.org/hhrutter/pdflib) [![stability-stable](https://img.shields.io/badge/stability-stable-green.svg)](https://github.com/emersion/stability-badges#stable) [![GoDoc](https://godoc.org/github.com/hhrutter/pdflib?status.svg)](https://godoc.org/github.com/hhrutter/pdflib) [![Coverage Status](https://coveralls.io/repos/github/hhrutter/pdflib/badge.svg?branch=master)](https://coveralls.io/github/hhrutter/pdflib?branch=master) [![Go Report Card](https://goreportcard.com/badge/github.com/hhrutter/pdflib)](https://goreportcard.com/report/github.com/hhrutter/pdflib) [![License: MIT](https://img.shields.io/github/license/mashape/apistatus.svg)](https://opensource.org/licenses/MIT) 
 
 # pdflib: a golang pdf processor

Package pdflib is a simple PDF processing library written in [Go](http://golang.org)
It provides both an API and a command line tool.
Supported are all versions up to PDF 1.7 (ISO-32000).

### Motivation

Reducing the size of large PDF files for mass mailings by optimization to the bare minimum.
This can be achieved by analyzing a PDF's cross reference table, removing redundant embedded resources like font files or images and by always writing back the file maxing out PDF compression.

I also wanted to have my own swiss army knife for PDFs written entirely in [Go](http://golang.org) that allows me to trim, split and merge PDF content.

### Features
* Validate (validates PDF files up to version 7.0)
* Read (builds xref table from PDF file)
* Write (writes xref table to PDF file)
* Optimize (gets rid of redundancies like duplicate fonts, images)
* Split (split a multi page PDF file into single page PDF files)
* Merge (a set of PDF files into one consolidated PDF file)
* Trim (generate a custom version of a PDF file)
* Extract Images (extract all embedded images of a PDF file into a given dir)
* Extract Fonts (extract all embedded fonts of a PDF file into a given dir)
* Extract Pages (extract specific pages into a given dir)
* Extract Content (extract the PDF-Source into given dir)
* Extract Text (extract the text of the PDF to an io.Reader)

### Installation
`go get github.com/hhrutter/pdflib/cmd/...`


### Usage

	pdflib is a tool for PDF manipulation written in Go.

	Usage:

	pdflib command [arguments]

 	The commands are:

	validate	validate PDF against PDF 32000-1:2008 (PDF 1.7)
	optimize	optimize PDF by getting rid of redundant page resources
	split		split multi-page PDF into several single-page PDFs
	merge		concatenate 2 or more PDFs
	extract		extract images, fonts, content, pages out of a PDF
	trim		create trimmed version of a PDF
	version		print pdflib version

	Single-letter Unix-style supported for commands and flags.

	Use "pdflib help [command]" for more information about a command.

    pdflib validate [-verbose] [-mode strict|relaxed] inFile
    pdflib optimize [-verbose] [-stats csvFile] inFile [outFile]
    pdflib split [-verbose] inFile outDir
    pdflib merge [-verbose] outFile inFile1 inFile2 ...
    pdflib extract [-verbose] -mode image|font|content|page [-pages pageSelection] inFile outDir
    pdflib trim [-verbose] -pages pageSelection inFile outFile

 [Please read the documentation ](https://godoc.org/github.com/hhrutter/pdflib)


### Status

Version: 0.0.1-beta

The extraction code for font files and images is experimental and serves as proof of concept only.


### To Do

* validation of the less used page entry "PresSteps"
* validation of the less used root entries "SpiderInfo", "Permissions", "Legal", "Collection"

I am looking for test PDFs using one of these features. If you have one and you can share let me know.
I am also accepting PRs but right now only regarding the defined items on the todo list.


### Disclaimer
Usage of pdflib assumes you know about and respect all copyrights of any PDF content you may be processing. This applies to the PDF files as such, their content and in particular all embedded resources like font files or images.


### License
MIT




	
