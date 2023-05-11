# OBJECT MODEL
- workbook: collections of objects for entire workbook
- worksheet: collections of objects for entire worksheet
	gives access to range objects
- range: contiguous cells
- ranges are used to create Tables, Charts, Shapes, and other viz's

SYNTAX FOR OFFICE SCRIPT

* Logging worksheet name

function main(workbook: ExcelScript.Worbook){

	let sheet = workbook.getActiveWorksheet(); //access to worksheet objects
	
	console.log(sheet.getName());
}

* Ranges (A1 notation style) 
	Core properties: [getValues,setValues,getFormulas,setValues,getFormat,setFormat]
	//easy way to remember: getter - setter : [Very Friendly Friend]
	
	use 2D arrays as in VBA


* Working with ranges

function main(workbook: ExcelScript.Workbook){
	let sheet = workbook.getActiveWorksheet();
	
	//headers and formatting
	let headers = [[]]	//feed headers in headers within square parenthesis
	let headerRange = sheet.getRange("") //enter range in a1 style
	
	headerRange.setValues(headers); //sets header value to defined range in headerRange
	headerRange.getFormat().getFill().setColor("");
	headerRange.getFormat().getFont().setColor("");
	
	//create databody range
	let rawData = [["Almonds",5,1],[a1,a2,a3],...[..]]; //add ordered data corresponding to headers
	
	let dataRange = sheet.getRange("") //set data range
	dataRange.setValues(rawData)
	
	//creating formulae
	let totalFormulas = [
		["=C3*D3"],["=SUM(E3:E5)"],["=my_formula_as_in_excel"],..[...]
													];
	let totalRange = sheet.getRange("E3:E5");
	totalRange.setFormulas(totalFormulas);
	totalRange.getFormat().getFont().setBold(true); //note boolean in lower case
	
	//display in number formatting prescribed
	totalRange.setNumberFormat("£0.00");
	
}

* Range data types
	-string, number, boolean = what value expecting from a cell or range? E.g.
		let prices = priceRange.getValues() as number[][];

	- blank cells are counted as Null e.g. 2,4,<null> will compute average with <null> if in range!
	
	- const arr = [1,2,3]
		arr.forEach(i => console.log(i)); //no way to stop forEach unless exception

	- a.map(function(s){ return s.length }) = a.map( s => s.length ); //ECMAscript 6 arrow func 
	  "[arg] => {my_code}" same as "function(arg) {my_code}" //shorthand, same in m script



	