---
name: MV BASIC Syntax
description: MV BASIC (MultiValue BASIC) language syntax, statements, and programming constructs. Automatically applied when working with MV BASIC files.
applyTo: "**/*"
---

# MV BASIC Language Reference

You are assisting a developer writing **MV BASIC** (MultiValue BASIC), a language used with UniVerse, UniData, and jBASE database systems. MV BASIC is case-insensitive. Programs operate on **dynamic arrays** with a hierarchical delimiter structure.

## Delimiters and Dynamic Arrays

MV BASIC uses a hierarchical delimiter system for data storage:

- **@AM** (Attribute Mark, CHAR(254)) — separates attributes (fields)
- **@VM** (Value Mark, CHAR(253)) — separates values within an attribute
- **@SM** (Sub-Value Mark, CHAR(252)) — separates sub-values within a value
- **@FM** is an alias for @AM (Field Mark)
- **@TM** (Text Mark, CHAR(251)) — rarely used

Dynamic arrays are strings containing these delimiters. Access elements with angle brackets:

```basic
value = RECORD<3>          ;* Third attribute
value = RECORD<3,2>        ;* Second value of third attribute
value = RECORD<3,2,1>      ;* First sub-value of second value of third attribute
```

## Program Structure

```basic
PROGRAM ProgramName
* or
SUBROUTINE SubName(param1, param2)
* or
FUNCTION FuncName(arg1)

* Variable declarations (optional but recommended)
EQU TRUE$ TO 1
EQU FALSE$ TO 0
COMMON /BLOCK/ VAR1, VAR2

* Main code here

IF is_subroutine THEN RETURN
IF is_function THEN RETURN(value)
STOP ; END
```

## Variable Declaration

```basic
EQU CONST.NAME TO value        ;* Named constant
EQUATE CONST.NAME TO value     ;* Same as EQU
DIM ARRAY(10)                  ;* Dimensioned array
DIM MATRIX(5,5)                ;* Two-dimensional array
COMMON /NAMED/ VAR1, VAR2     ;* Named common block (shared between programs)
COMMON VAR1, VAR2              ;* Unnamed common block
```

## File I/O Operations

```basic
* Opening files
OPEN "","FILENAME" TO file.var ELSE STOP 201,"FILENAME"
OPEN "","DICT FILENAME" TO dict.var ELSE STOP 201,"DICT FILENAME"

* Reading records
READ record FROM file.var, id ELSE record = ""
READV value FROM file.var, id, attr# ELSE value = ""
MATREAD array FROM file.var, id ELSE MAT array = ""
READU record FROM file.var, id LOCKED
   CRT "Record locked"
END ELSE
   record = ""
END

* Writing records
WRITE record ON file.var, id
WRITEV value ON file.var, id, attr#
MATWRITE array ON file.var, id

* Deleting records
DELETE file.var, id

* Releasing locks
RELEASE file.var, id
RELEASE                        ;* Release all locks
```

## SELECT / Query Operations

```basic
* Select all records from a file
SELECT file.var
* or with query criteria
EXECUTE "SELECT CUSTOMERS WITH STATE = 'CA'" CAPTURING output

* Process selected records
LOOP
   READNEXT id ELSE EXIT
   READ record FROM file.var, id ELSE CONTINUE
   * Process record
REPEAT

* CLEARSELECT to clear active select list
CLEARSELECT
```

## Control Flow

```basic
* IF/THEN/ELSE
IF condition THEN
   statements
END ELSE
   statements
END

* Single-line IF
IF condition THEN statement ELSE statement

* CASE statement
BEGIN CASE
   CASE condition1
      statements
   CASE condition2
      statements
   CASE 1                     ;* Default case
      statements
END CASE

* FOR/NEXT loop
FOR i = 1 TO count STEP 1
   statements
NEXT i

* LOOP/REPEAT
LOOP
   statements
WHILE condition DO
   statements
REPEAT

* LOOP/UNTIL
LOOP
   statements
UNTIL condition
REPEAT

* GOTO / GOSUB
GOTO label
GOSUB label
RETURN
```

## String Functions

```basic
LEN(string)                    ;* Length of string
TRIM(string)                   ;* Remove leading/trailing spaces
TRIMF(string)                  ;* Trim front
TRIMB(string)                  ;* Trim back
INDEX(string, substr, occur)   ;* Find substring occurrence
FIELD(string, delim, field#)   ;* Extract delimited field
FIELDS(string, delim, start, count)
COUNT(string, substr)          ;* Count occurrences
DCOUNT(string, delim)          ;* Count delimited fields
UPCASE(string)                 ;* Convert to uppercase (or OCONV(str,"MCU"))
DOWNCASE(string)               ;* Convert to lowercase (or OCONV(str,"MCL"))
ALPHA(string)                  ;* Test if alphabetic
NUM(string)                    ;* Test if numeric
SPACE(n)                       ;* Generate n spaces
STR(string, n)                 ;* Repeat string n times
CHANGE(string, old, new)       ;* Replace occurrences
CONVERT old TO new IN string   ;* Character-by-character conversion
string[start, length]          ;* Substring extraction
```

## Dynamic Array Functions

```basic
INSERT(dynarray, attr; val; subval; value)
EXTRACT(dynarray, attr, val, subval)
REPLACE(dynarray, attr, val, subval; value)
DELETE(dynarray, attr, val, subval)
LOCATE value IN dynarray<attr,val> BY "AL" SETTING pos ELSE
   INS value BEFORE dynarray<attr,pos>
END
INS value BEFORE dynarray<attr,val,subval>
DEL dynarray<attr,val,subval>
```

## Conversion Functions

```basic
ICONV(value, conversion)       ;* Input conversion (external to internal)
OCONV(value, conversion)       ;* Output conversion (internal to external)
FMT(value, format)             ;* Format for display

* Common conversion codes:
* "D"     - Date (days since 12/31/1967)
* "D4/"   - Date as MM/DD/YYYY
* "MT"    - Time (seconds since midnight)
* "MR2"   - Decimal 2 places (implied)
* "MD2"   - Decimal 2 places (stored with decimal)
* "MCU"   - Uppercase
* "MCL"   - Lowercase
* "G0.1"  - Group extraction

DATE()                         ;* Current internal date
TIME()                         ;* Current internal time
TIMEDATE()                     ;* Formatted date/time string
```

## Output Statements

```basic
CRT expression                 ;* Print to terminal (CRT)
PRINT expression               ;* Print to terminal or printer
DISPLAY expression             ;* Same as CRT
CRT expression :               ;* Suppress newline with colon
PRINT ON channel expression    ;* Print to specific print channel
INPUT variable                 ;* Read from terminal
INPUT variable, length         ;* Read with max length
INPUT variable :               ;* Input without newline
```

## Subroutines and Functions

```basic
* Calling subroutines
CALL SUBNAME(arg1, arg2, arg3)
CALL @VARIABLE(arg1)           ;* Indirect call

* Defining subroutines
SUBROUTINE SUBNAME(param1, param2, param3)
   * code
RETURN

* Defining functions
DEFFUN FUNCNAME(arg1) CALLING "FUNCNAME"
FUNCTION FUNCNAME(arg1)
   * code
RETURN(result)
```

## Error Handling

```basic
* UniVerse style
PROGRAM.ERROR:
   CRT "Error: " : SYSTEM(0)
   STOP

* Modern TRY/CATCH (UniVerse 12+)
TRY
   statements
CATCH error
   CRT "Error caught: " : error
END TRY
```

## EXECUTE / System Commands

```basic
EXECUTE command CAPTURING output RETURNING status
EXECUTE command PASSLIST RTNLIST capturing output

* Check STATUS after operations
STATUS()                       ;* Returns status of last operation
SYSTEM(n)                      ;* System functions (various n values)
@SYSTEM.RETURN.CODE            ;* Return code from last EXECUTE
```

## Include and Pre-Processor

```basic
$INCLUDE FILENAME RECORD.NAME
$INCLUDE UNIVERSE.INCLUDE FILECONTROL.H
$DEFINE SYMBOL value
$IFDEF SYMBOL
$IFNDEF SYMBOL
$ENDIF
```

## Common @-Variables

```basic
@AM, @FM                       ;* Attribute/Field Mark
@VM                            ;* Value Mark
@SM, @SVM                      ;* Sub-Value Mark
@ID                            ;* Current record ID (in I-type)
@RECORD                        ;* Current record (in I-type)
@NI                            ;* Number of attributes
@SENTENCE                      ;* Command that invoked the program
@USER.NO                       ;* Port number
@WHO                           ;* Account name
@LOGNAME                       ;* Login name
@USERNO                        ;* User number
@PATH                          ;* Current directory path
@TRUE, @FALSE                  ;* Boolean constants
@NULL                          ;* Null value
```

## Operators

```basic
* Arithmetic: +  -  *  /  **  MOD
* String concatenation: :  (colon)
* Relational: =  #  <>  <  >  <=  >=  EQ  NE  LT  GT  LE  GE
* Logical: AND  OR  NOT
* Pattern match: MATCHES  MATCH
* Assignment: =  +=  -=  :=
```

## Important Conventions

- Comments start with `*` (full line), `!` (full line), or `;*` (inline after semicolon)
- `REM` is also a comment keyword
- Labels end with colon: `LABEL.NAME:`
- Statements can be on one line separated by `;`
- Variable names are typically UPPERCASE with dots: `CUSTOMER.NAME`
- Record IDs are often stored in variables ending in `.ID`
- File variables often end in `.F` or `.FILE`: `CUSTOMERS.F`
