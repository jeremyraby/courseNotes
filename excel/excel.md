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

## Helpful stuff (& things)

- Named cells
  - Helpful for naming a cell which can then be referenced as a constant in a formula
    - Compound interest formula can be done with named cells
      - see [here](/Users/jeremyraby/Documents/development/courseNotes/excel/namedCells.jpg)
    - There is also a "Name Manager" in the Formulas tab --> Defined Names group where you can update the formula or cell name
  - Can also name ranges
- Macros
  - By default, when recording macros, the cell that was active during the first step will *always* will be used when that macro is run later. *However* you can select Developer tab --> Use Relative References *before* recording the macro so you can run the macro in whichever cell you wish.

### Common Errors

|Code | Likely reason(s) |
| --- | --- |
| `#DIV/0!` | You're trying to divide by 0 inside a formula |
| `#NAME?` | Function name or variable name isn't recognized |
| `#NUM!` | Number error, invalid argument or the number is too big for Excel |
| `#REF!` | Cell reference not valid - probably has been deleted |
| `#VALUE!` | Wrong data type used in argument |
| `####` | Cell is too narrow to display result |
