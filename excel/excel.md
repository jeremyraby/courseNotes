# Excel

## Shortcuts

- `Cmd + arrow` keys jump to first/last cell in that column (up/down) or row (left/right)
- To copy worksheets to new workbooks
  1. Create a new workbook
  2. Right-click the old sheet you want copied
  3. Select "Move or copy"
  4. Select the new workbook from the "To book:" dropdown
- `Shift + arrow` keys will select multiple individual cells
- `Cmd + Shift + arrow` will select multiple cells at once
- `Fn + Ctrl + left arrow` will make A1 the active cell
- To move the active cell inside a selection
  - `Ctrl + .` moves it clockwise
  - `Return` moves it down
  - `Shift + Return` moves it up
  - `Tab` moves it right
  - `Shift + Tab` moves it left
- Fill series, in the Edit group will allow you to auto fill rows or columns based on some constant interval, eg 10, 20, 30, 40, 50, 60, 70, 80, 90, 100
- Excel has "lists" of things that are commonly used and will be included in an autofill situation. Monday, Tuesday.../Jan, Feb... are examples. You can make a "Custom list" for serials of commonly used items, like listing the X-Men:
  1. Open the Excel menu in the top left of the window
  2. Excel --> Preferences --> Formulas and Lists --> Custom Lists
  3. Add in your list. Can be typed in manually or added from a range of cells
- `Fn + F4`, when in a formula will add `$` for absolute references. Multiple presses will cycle through relative, mixed, and absolute references
- `Ctrl + ;` will enter current date

## Helpful stuff (& things)

- Named cells
  - Helpful for naming a cell which can then be referenced as a constant in a formula
    - Compound interest formula can be done with named cells
      - see [here](/Users/jeremyraby/Documents/development/courseNotes/excel/namedCells.jpg)
    - There is also a "Name Manager" in the Formulas tab --> Defined Names group where you can update the formula or cell name
  - Can also name ranges
- Dynamic Named Ranges
  - If you just use a "static" named range and refer to it in another formula, the formula won't update if you add data to the bottom of the range.
    - Use the `=OFFSET()` & `=COUNT()` functions to set up an array that will automatically update as new data are added. [Learn more](https://www.ablebits.com/office-addins-blog/excel-dynamic-named-range/)
- Macros
  - By default, when recording macros, the cell that was active during the first step will *always* will be used when that macro is run later. *However* you can select Developer tab --> Use Relative References *before* recording the macro so you can run the macro in whichever cell you wish.
  - Can also make user-defined functions with VBA
- Finding blanks
    1. Select range
    2. Editing group --> Find & Select --> Go To... --> Special --> Blanks {blanks will be selected}
    - Editing group --> Find & Select --> Go To Special... will do this faster
    - `Fn + F5` will bring up the Go To... dialog box
    3. Highlight blanks
  - Can also use Conditional Formatting to highlight blanks (probably better)
- `=FILTER()` is probably better than using the Sort & Filter group because it keeps the original data intact and can be updated dynamically if more data are entered
- Formatting data as a table will allow you to add data and have calculations be updated automatically. Converting data to a table can spare you the headache of creating dynamic named ranges, updating formula references, copying formulas across columns, formatting, filtering and sorting your data. [More info](https://www.ablebits.com/office-addins-blog/excel-table-tutorial/)
- Pivot Tables
  - Used for comparing 2+ columns against each other
  - The column that has more unique values (games played vs teams) should go in the Rows data field & the column that has fewer unique values (teams vs games played) should go in the Columns data field
  - Columns on which should have calculations performed (average, count, display as a percentage, etc) should go in the Values data field

**Common Errors**

|Code | Likely reason(s) |
| --- | --- |
| `#DIV/0!` | You're trying to divide by 0 inside a formula |
| `#NAME?` | Function name or variable name (like a named cell) isn't recognized |
| `#NUM!` | Number error, invalid argument or the number is too big for Excel |
| `#REF!` | Cell reference not valid - probably has been deleted |
| `#VALUE!` | Wrong data type used in argument |
| `####` | Cell is too narrow to display result |

## Functions

- To search for a function, click the f(x) button next to the formula bar
  - There's also the Formulas tab --> Function Library
- `=COUNTA()` counts non-empty cells, `=COUNT()` only counts cells with numbers

> Dates are stored as serial numbers and will skew aggregate functions (SUM, AVERAGE)

- `=LARGE(array, qualifier)` allows you to find the 1st, 2nd, etc largest values in an array. `=SMALLEST(array, qualifier)` does the opposite
  - [see here](/Users/jeremyraby/Documents/development/courseNotes/excel/largestFunction.jpg)
  - be sure to use absolute referencing
- Use `=RAND()` to randomly sort a list of (*x*)
  1. List (*x*) in one column
  2. Copy + paste `=RAND()` into adjacent column
  3. Select both columns
  4. Editing group --> Sort & Filter --> Custom Sort... --> Sort by column with random numbers (choose ASC or DESC)
  5. Can now delete column with random numbers and you have a randomly sorted list
- `=RANDARRAY()` will create an X * Y array with random numbers filled in that can either be decimal or integer
- `=CHOOSE()` will reference an array and choose which value to display in the cell
- For splitting text with `=LEFT()` & `=RIGHT()`
  - `=LEFT({variable},FIND("{delimiter}",{variable})-1)`
  - `=RIGHT({variable},LEN({variable})-FIND("{delimiter}",{variable}))`
- For financial functions (PMT, FV, PV)
  - Income from a financial institution is always `+` while payments made to financial institutions are always `-`.
    - Dividends, loans, interest = `+`
    - Loan payments, deposits = `-`
      - will return in red text written in parantheses (150.25)
- Array formula
  - `={COLUMNS;ROWS}` --> `={1,2,3;4,5,6}` -->
  
  | 1 | 2 | 3 |
  | --- | --- | --- |
  | 4 | 5 | 6 |
  - [Arrays (or vectors {single column array}) can be multiplied by each other and these formulas can replace tons of others](https://www.ablebits.com/office-addins-blog/array-formulas-functions-excel/)
- `=IFS()` can chain if statements in one function
- `=SUMIFS()` & `=COUNTIFS()` will aggregate based on multiple conditions
