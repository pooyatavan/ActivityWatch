# ActivityWatch Scripts (Import / Export)

This project collects ActivityWatch data from all your systems and imports it into a central server so you can see activity for every machine in one place.

- **Export**: The export script reads all data from ActivityWatch via its API, saves it to a JSON file, and uploads that file to OneDrive.
- **Import**: The import script deletes every existing bucket from the previous run, then imports and updates all buckets from the JSON files stored in OneDrive back into ActivityWatch.

## :computer: Instruction for Clients

## Step 1 - Download from github
1. in github repositorie click green button "Code"
2. from menu click "download zip" to download start
3. extract it from zip and copy "export" folder and paste it in "C:\" drive root

## Step 2 - ActivityWatch

Download Link: [ActivityWatch](https://activitywatch.net/)
- download and Install ActivityWatch with the default settings on all computers that you want to track.

## Step 3 - OneDrive

Install OneDrive (most Windows machines include it by default; if not, download and install it).
1. open OneDrive application on your computer
2. Sign in **OneDrive account** on all computers.
- All clients and the server must use a single shared OneDrive account to access the same sync folder.

## Step 4 - Convert bat file to exe

To avoid the black command prompt window appearing every time the script runs, convert the .bat file to an .exe using a "bat to exe" tool.
- Tool: [Bat To Exe Converter](https://www.majorgeeks.com/mg/getmirror/bat_to_exe_converter,1.html)

1. Install and open the app and load your run.bat file(import or export bat file) from "c:\export"
2. In the Options tab, set the EXE format to: "64-bit Windows | Screen (Invisible)".
3. Click Convert (choose 64-bit or 32-bit depending on your machines).
4. make sure exe file we create it placed in "c:\export" path

## Step 5 - Windows Task Scheduler

Use Windows Task Scheduler to automate export/import so it runs every 30 minutes (or any schedule you prefer).

1. from "start" menu search "Task scheduler" and open it.
2. from right window click on "create basic task".
3. choose a name for it and click next
4. Set "Trigger" to "One time" and click next
5. in "Action" select "Start a program" and click next
6. in "Start a program" browse the exe file that you create it in Step 3 and click next
7. click finish
8. in left menu click on "Task Scheduler Library"
9. from list find your Task you create, and duble click on task to edit window appear.
10. in "Trigger" tab click edit
11. Set Checked "Repeat task every" and set time for it (minutes or hours).
12. Set "For a duration of" to "Indefinitely".

## :computer: Instruction for Server
## Step 1 - Download from github
1. click green button "Code"
2. from menu click "download zip" to download start
3. extract it and copy "import" folder and paste it in "C:\" drive root

## Step 2 - ActivityWatch

Download Link: [ActivityWatch](https://activitywatch.net/)

download and Install ActivityWatch with the default settings on all computers that you want to track.

## Step 3 - OneDrive

Install OneDrive (most Windows machines include it by default; if not, download and install it).
1. open OneDrive application on your computer
2. Sign in **OneDrive account** on all computers.
- All clients and the server must use a single shared OneDrive account to access the same sync folder.
- 
## Step 4 - Convert bat file to exe

To avoid the black command prompt window appearing every time the script runs, convert the .bat file to an .exe using a "bat to exe" tool.
Tool: [Bat To Exe Converter](https://www.majorgeeks.com/mg/getmirror/bat_to_exe_converter,1.html)

1. Install and open the app and load your run.bat file(import or export bat file) from "c:\import"
2. In the Options tab, set the EXE format to: "64-bit Windows | Screen (Invisible)".
3. Click Convert (choose 64-bit or 32-bit depending on your machines).
4. make sure exe file we create it placed in "c:\import" path

## Step 5 - Python
1. download and install Python [Python](https://www.python.org/)
2. in install window checked the "add python.exe to path"
3. open command prompt from start menu
4. copy and psate these commands to create environment and install lib:
   ```bash
   python -m venv c:\import\myenv
   cd c:\import\myenv
   Scripts\activate
   pip install aw_client --no-cache-dir
   pip install requests --no-cache-dir
    ```
   
## Step 6 - Windows Task Scheduler

Use Windows Task Scheduler to automate export/import so it runs every 30 minutes (or any schedule you prefer).

1. from "start" menu search "Task scheduler" and open it.
2. from right window click on "create basic task".
3. choose a name for it and click next
4. Set "Trigger" to "One time" and click next
5. in "Action" select "Start a program" and click next
6. in "Start a program" browse the exe file that you create it in Step 4 and click next
7. click finish
8. in left menu click on "Task Scheduler Library"
9. from list find your Task you create, and duble click on task to edit window appear.
10. in "Trigger" tab click edit
11. Set Checked "Repeat task every" and set time for it (minutes or hours).
12. Set "For a duration of" to "Indefinitely"


> [!IMPORTANT]
> - Use OneDrive if you do not already have a cloud storage service (reliable and pre-installed on most Windows machines).
> - To use another cloud provider, update the paths in the scripts to point to that service's sync folder
> - All paths in this project are configured for OneDrive. If you want to use another cloud service, update the paths in the scripts accordingly.
