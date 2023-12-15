# Google Sheets

Web-based and collaboration-oriented spreadsheet program, part of Google's suite of products.

Organized by Ahmed Thahir

## Recording

Watch the [Recording](https://drive.google.com/file/d/1OoVMuNGAEF4AwfeJni7Q77pKvqUktSFg/view)

## Event Spreadsheet

Open and explore the [Google Sheet](https://docs.google.com/spreadsheets/d/1MyMfDYq6oYnbcQ_JOxwTxRQhKBKGfWco6h6bQsPJQ5o/view) created for this event!

## Why not use spreadsheets?
- Faster
- Data and analysis are separate
- Automate analysis
- Reproducibility
- Python is open-source, hence the analysis is open-source

## Number Formatting

```
#,##0; [red]#,##0; -
```
+ve numbers usual
-ve numbes red
0 as -

## Cell Formatting
Conditional Formatting for Empty
Alternating Colors for Rows
Enhances legibility

## Formulae

### Value in $n^{th}$ row
```c
=INDEX(Payable!A2:A100, 5)
```

#### Value in Last Row

```c
=INDEX(Payable!A2:A, COUNTA(Payable!A2:A))
```

### Automatic Numbering
```c
=ARRAYFORMULA( if( ISBLANK(B2:B100), , row(B2:B100)-1 ) )

=ARRAYFORMULA( if( ISBLANK(B4:B100), , row(B4:B100)-3 ) )
```

### Autofill Particular Word
```c
=ARRAYFORMULA( if(ISBLANK(C2:C100), "-", "Al Quoz") )
```

### Natural Join

Uses  `VLOOKUP`

```mysql
= VLOOKUP(look_for_range, look_in_range, columns, sorted_always_FALSE)
```

### Single Column

```mysql
=ARRAYFORMULA(if( ISBLANK(C2:C100), "-",
	VLOOKUP(C2:C100,'Student Details'!$A$2:$B100, 2, FALSE)
))
```

#### Multiple Columns

Make sure that the look_in_range is correct size

```mysql
=ARRAYFORMULA(if( ISBLANK(C2:C100), "-",
	VLOOKUP(C2:C100,'Student Details'!$A$2:$D100, {2, 3, 4}, FALSE)
))
```

### Count number of capital/small letters

#### Capital

```mysql
=SUMPRODUCT(LEN(E3)-LEN(SUBSTITUTE(E3,CHAR(ROW(INDIRECT("65:90"))),"")))
```

#### Small

```mysql
=SUMPRODUCT(LEN(E3)-LEN(SUBSTITUTE(E3,CHAR(ROW(INDIRECT("97:122"))),"")))
```

### Import Data from another sheet

```mysql
=ImportRange("1WsMosP6WaifrDsTaMuZUlEP8MSYP1nfTyKh9x7q4ads","Student_Details!B2:B200")
```

### Check if value in another column / `not in` of sql

```mysql
=ARRAYFORMULA(IF(ISBLANK(F2:F), ,
	NOT(
		IFERROR(
			MATCH(J2:J, I2:I, 0)/MATCH(J2:J, I2:I, 0),
			0
		)
	)
	)
)
```

## Functionality

Dropdown

Data Validation > List

### Automatic Checkboxes

Data Validation > Checkboxes

## Query

Quite similar to mySQL

### Tips

- Put `where col is not null` whenever possible to prevent crashes (due to too many blank values)
- Use only required columns in the input_range
- Use fixed ranges

### Basic

```mysql
=QUERY(People!A2:Z, "
select B
where B is not null
")

## or (better way)

=QUERY(QUERY(People!A2:Z), "
select Col2
where Col2 is not null
")
```

### Labels

```mysql
=QUERY(QUERY(People!A2:Z), "
select Col2
where Col2 is not null
label Col2 'Roles'
")
```

### Distinct

```mysql
=UNIQUE(
QUERY(QUERY(People!A2:Z), "
select Col2
where Col2 is not null
"))
```

### Sorting

```mysql
=QUERY(QUERY(Teams!A2:Z), "
select Col2, count(Col2)
where Col2 is not null
group by Col2
order by count(Col2) desc
")
```

### Double Grouping

```mysql
=QUERY(QUERY(Teams!A2:Z), "
select C, B, count(B)
where C is not null and B is not null
group by C, B
order by count(B) desc
")
```

### Rounding

```mysql
=QUERY(
D2:E,
"select 10/3 format 10/3 '#.#' "
)
```

### Calculating %

This query will automatically multiply with 100

```mysql
=QUERY(
D2:E,
"select 10/3 format '#.## %' "
)
```

### Using Cell as value

#### Number

```mysql
=QUERY(
D2:E,
"select 10/"&E2&""
)
```

### Text

Has `'` around the `"`

```mysql
=QUERY(
D2:E,
"select '"&E2&"'
)
```

### Subquery

```mysql
=QUERY(QUERY(People!B2:D, "
select B, count(B)
where B is not null
group by D, B
label B 'Important Divisions', count(B) 'Size'
"), "
select Col1, avg(Col2), count(Col1)
where Col1 is not null
group by Col1 order by avg(Col2) desc
label count(Col1) 'No of Teams', avg(Col2) 'Average Size'
")
```

```mysql
=QUERY(QUERY(People!B2:D, "
select B, count(B) where B is not null group by D, B label B 'Important Division', count(B) 'Size'"
), "
select Col1, count(Col2), avg(Col2), avg(Col2)/"&E2&", min(Col2)
where Col1 is not null
group by Col1
order by count(Col2) desc, avg(Col2)/"&E2&" desc
label min(Col2) 'Min Size', avg(Col2) 'Avg Size', avg(Col2)/"&E2&" 'Avg Size %', count(Col2) 'Teams having'
format avg(Col2)/"&E2&" '#.## %' "
		  )
```

## Administrative Permission

### Read (Viewers)

Set sharing settings of the entire gsheet as view only

### Read

Protect Sheet

Description - Summary

### Read/Write/Update (Lock Schema)

Protect header row

Description - Header

### Read/Update (not create/modify/delete)

Create a blank column

Protect the column from editing

Description - Update Only

Hide the column

## Dashboards

Even Google Sheets can create dashboard

Generate Charts by

- File > Share > Publish to Web
- Select what to include

## Import into Python

```python
url = "" ## excel publish link from google sheets
```

```python
sheet = pd.read_excel(
url,
sheet_name = "Not_Interviewed",
usecols = [
"Name",
"Email",
"Year"
]
)

sheet = pd.read_excel(
url,
sheet_name = "Interview_Summary",
header = 2,
usecols = [0, 3]
)
```

## Big Series Generation

### Uni Hours of the week

```mysql
=FLATTEN(
ARRAYFORMULA(CONCAT("M", TEXT(SEQUENCE(9), "0"))),
ARRAYFORMULA(CONCAT("T", TEXT(SEQUENCE(9), "0"))),
ARRAYFORMULA(CONCAT("W", TEXT(SEQUENCE(9), "0"))),
ARRAYFORMULA(CONCAT("Th", TEXT(SEQUENCE(9), "0"))),
ARRAYFORMULA(CONCAT("F", TEXT(SEQUENCE(9), "0")))
)
```

## Regex

```
f20[0-9|A-Z]+@dubai.bits-pilani.ac.in
```

## Web Scraping using [[Google Sheets]]

```mysql
=importxml(
"[Products. Nike SG](https://www.nike.com/sg/w/sale-3yaep",)
"//div[@class='product-card__title']"
)
```


