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
mkdir my-folder

<img width="377" height="153" alt="Screenshot (661)" src="https://github.com/user-attachments/assets/de28fd02-ec19-4955-8c7f-46fd16400be9" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"

rmdir my-folder

<img width="398" height="113" alt="Screenshot (662)" src="https://github.com/user-attachments/assets/cd803a48-0255-4adb-a38f-1f85ea3b8121" />


## COMMAND AND OUTPUT


Create the file Rose.txt
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z
1 file(s) copied
dir Rose.txt

<img width="815" height="283" alt="Screenshot (663)" src="https://github.com/user-attachments/assets/95dae534-fa47-40e0-b9b3-80e90e8e0861" />


## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection

echo “hello world” > hello.txt
type hello.txt

<img width="457" height="83" alt="Screenshot (664)" src="https://github.com/user-attachments/assets/b38cb881-f63a-4073-ae1d-b2e74e1ded0d" />

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
copy hello.txt hello1.txt

<img width="560" height="109" alt="Screenshot (665)" src="https://github.com/user-attachments/assets/179edc95-b7c7-4ce5-9404-9882b46bff6e" />

## COMMAND AND OUTPUT

Remove the file hello1.txt
del hello1.txt
dir hello1.txt

<img width="363" height="128" alt="Screenshot (666)" src="https://github.com/user-attachments/assets/0619ebde-fdac-4694-8fc0-c1d287741213" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
assoc | more
<img width="499" height="506" alt="Screenshot (667)" src="https://github.com/user-attachments/assets/321e9f50-5fb3-44b7-80b4-75e2636824e5" />


## COMMAND AND OUTPUT

List out all the associated file extensions 
fc hello.txt Rose.txt

<img width="689" height="128" alt="Screenshot (668)" src="https://github.com/user-attachments/assets/94c953b1-6a82-4ea2-8604-b3a51ed462c8" />


## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

BATCH SCRIPT
Open Notepad with filename 1.bat and type the following batch script
@echo off
set name=John
echo Hello, %name%!
pause

## OUTPUT

<img width="725" height="263" alt="Screenshot (670)" src="https://github.com/user-attachments/assets/59174e4b-4f5a-4e5e-b6fb-282661bfd75e" />

Execute the batch file 1.bat

<img width="246" height="54" alt="Screenshot (671)" src="https://github.com/user-attachments/assets/5b8e567d-8336-4133-a783-b29d343cdd19" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

Open Notepad with filename 2.bat and type the following and execute 2.bat
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause


## OUTPUT


<img width="773" height="230" alt="Screenshot (672)" src="https://github.com/user-attachments/assets/94104385-01e7-41c9-997b-bef5bdc74b2b" />


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

Open Notepad with filename 3.bat and type the following and execute 3.bat
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

## OUTPUT

<img width="786" height="195" alt="Screenshot (673)" src="https://github.com/user-attachments/assets/d4716850-cc07-4a3a-98c5-ae5e184865e2" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
Open Notepad with filename 4.bat and type the following and execute 4.bat
Then create the file sample.txt and execute 4.bat

@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause


## OUTPUT


<img width="803" height="190" alt="Screenshot (674)" src="https://github.com/user-attachments/assets/009eb6e4-d498-4384-968a-941f4c68dbd3" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

Open Notepad with filename 5.bat and type the following and execute 5.bat

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

## OUTPUT

<img width="778" height="265" alt="Screenshot (675)" src="https://github.com/user-attachments/assets/c3442bb0-d06a-4176-b81f-22832167bae9" />


# RESULT:
The commands/batch files are executed successfully.

