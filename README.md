# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
```
mkdir my-folder
```
<img width="511" height="61" alt="Screenshot 2026-03-17 000845" src="https://github.com/user-attachments/assets/7874adf2-4bd5-4a70-b794-a9415be50c50" />

## COMMAND AND OUTPUT
Remove the directory "my-folder"
```
rmdir my-folder
```
<img width="508" height="58" alt="Screenshot 2026-03-17 001001" src="https://github.com/user-attachments/assets/5451ff46-a2af-44a9-a680-d159e7c04f47" />

## COMMAND AND OUTPUT
Create the file Rose.txt
```
type nul > Rose.txt
```
<img width="547" height="66" alt="Screenshot 2026-03-17 001116" src="https://github.com/user-attachments/assets/faf684da-b06f-41ae-b8cc-378e4e0ad125" />

## COMMAND AND OUTPUT
Create the file hello.txt using echo and redirection
```
echo Hello World > hello.txt
```
<img width="695" height="63" alt="Screenshot 2026-03-17 001224" src="https://github.com/user-attachments/assets/28fd2269-8f3a-465b-8a8b-b7da699a5f94" />

## COMMAND AND OUTPUT
Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
<img width="614" height="75" alt="Screenshot 2026-03-17 001328" src="https://github.com/user-attachments/assets/57251ff8-dfaa-4fa5-ae9c-78d8f05c36e3" />

## COMMAND AND OUTPUT
Remove the file hello1.txt
```
del hello1.txt
```
<img width="484" height="53" alt="Screenshot 2026-03-17 001447" src="https://github.com/user-attachments/assets/303c5373-1f33-4179-a955-2d73c7a6e66f" />

## COMMAND AND OUTPUT
List out the file hello1.txt in the current directory
```
dir hello1.txt
```
<img width="544" height="223" alt="Screenshot 2026-03-17 001539" src="https://github.com/user-attachments/assets/aa3fb7bf-3c35-4b08-9812-0f0ddc3e3a16" />

## COMMAND AND OUTPUT
List out all the associated file extensions 
```
assoc
```
<img width="772" height="783" alt="Screenshot 2026-03-17 001742" src="https://github.com/user-attachments/assets/5687fa70-c789-491b-a07f-122ede51760d" />
<img width="771" height="321" alt="Screenshot 2026-03-17 001759" src="https://github.com/user-attachments/assets/4a445156-b268-4dd4-bbdc-23ed8c5b7179" />

## COMMAND AND OUTPUT
Compare the file hello.txt and rose.txt
```
fc hello.txt Rose.txt
```
<img width="674" height="189" alt="Screenshot 2026-03-17 001926" src="https://github.com/user-attachments/assets/5162a3fe-1b55-4ccf-b945-7d273d037fa8" />

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
## CODE
```
@echo off
set name=John
echo Hello, %name%
pause
```
## OUTPUT
<img width="621" height="97" alt="Screenshot 2026-03-17 002145" src="https://github.com/user-attachments/assets/d1982f1a-fa7a-41e6-bcf2-d2333296bcd4" /> 

Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
## CODE
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE

:END
echo Thank you!
pause
```

## OUTPUT
<img width="825" height="255" alt="Screenshot 2026-03-17 002342" src="https://github.com/user-attachments/assets/cd135235-e333-40e7-992f-e168e7cbdaba" />
Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```
## OUTPUT
<img width="564" height="195" alt="Screenshot 2026-03-17 002503" src="https://github.com/user-attachments/assets/80ca47e3-b347-4fcc-b6f7-7e27316580d2" />
Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.
## CODE
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```
Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## OUTPUT
<img width="536" height="66" alt="Screenshot 2026-03-17 002633" src="https://github.com/user-attachments/assets/b44c9d44-d138-4c88-bebc-06efe75bd200" />
Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU

:EXIT
echo Goodbye!
pause
exit
```
## OUTPUT1
<img width="521" height="251" alt="Screenshot 2026-03-17 002828" src="https://github.com/user-attachments/assets/9e42ad76-796b-4610-9447-777c5849ddb3" />
## OUTPUT2
<img width="543" height="242" alt="Screenshot 2026-03-17 002910" src="https://github.com/user-attachments/assets/4aca3df7-c250-4638-8cb8-5d526fd91f30" />
## OUTPUT3
<img width="535" height="232" alt="Screenshot 2026-03-17 003009" src="https://github.com/user-attachments/assets/d0566471-c239-4c01-87ca-b8b0bd6f1bc7" />
# RESULT:
The commands/batch files are executed successfully.

