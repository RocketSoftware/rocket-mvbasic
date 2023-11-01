# Known Issues

## Editing

**MVVS-309** The selected formatting alignment is not correct

**MVVS-399** Reference bug by scope cause

**MVVS-535** extremely slow to including U2MQI.H file for the parser

**MVVS-548** EQU could not work correctly in IF statement

**MVVS-590** READU statement syntax highlight incorrect and misleading

**MVVS-636** All lines of nonsense are accepted in editor

**MVVS-653** reporting syntax error for "open(line) = 1" in the parser

**MVVS-843** parser reporting syntax issue in APP.PROGS\AMLC

**MVVS-927** Variables name displayed in breadcrumbs rather than functions name in some cases

**MVVS-928** unable to display label name in the path line for subroutine

**MVVS-1003** Using a STOP statement to end a program instead of RETURN causes an indentation problem

**MVVS-1042** Incorrect grammar tip for the SWAP function

**MVVS-1054** Wrong documentation tips in some situations

**MVVS-1119** Formatting a document will format "$options -static.dim" to "$options - static.dim", resulting in incorrect code behavior

**MVVS-1136** enhancement request to avoid to add a blank line to the end of BASIC source code

## Compilation

**MVVS-867** build task is missing when debug BASIC in multi-workspace

**MVVS-918** compile BASIC with options for UniVerse account is not working

**MVVS-919** compile BASIC programs will list out nonexistent BASIC program

**MVVS-1007** unable to compile BASIC program which contains special characters in a string

**MVVS-1024** compile option not works for UniData account in MVVS 2.1.0 build

## Debugging

**MVVS-713** unable to step out at the end of call subroutine

**MVVS-795** Next, continue could not step out from subroutine in UV debugging, Only step in works. 

**MVVS-809** Debugger should not report "undefined variable" for field inside {}

**MVVS-857** Debugging hangs on subroutine RETURN

**MVVS-920** unable to debug BASIC program with launch.json file if there was an error in the configuration file

**MVVS-1008** Debug option can lose focus on terminal window

**MVVS-1188** An exception occurred when debug the program with local subroutine for the second time

**MVVS-1190** After pausing during a long for loop, continue button does not work

**MVVS-1205** Click F5, compilation pass but there is error line below code

**MVVS-1207** Debugger F5(continue) can't stop at breakpoint in subroutine

**MVVS-1210** Click stop debugging, then the file can't be edit

**MVVS-1211** Debug failed against a basic program(a correct basic program)

**MVVS-1222** Step Out is not working properly in MVVS 2.2.0 release

## Connection

**MVVS-671** Can't connect to UniData demo account on linux

**MVVS-1121** java throw exception when failed to connect to the UV account


## Others

**MVVS-982** "The RPC failed" error will crash VS Code extension

**MVVS-1036** User may not be aware of the change on the server side.

**MVVS-1055** Command 'extension.selectU2Server' not found

**MVVS-1156** Can not delete basic file under a customer account added to UV.ACCOUNTS
