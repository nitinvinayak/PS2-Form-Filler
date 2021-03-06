> Note: I have solved the issues reported for PS2 Sem1 20/21. Please create an issue if you
> encounter any further problems, with accurate decriptions and error logs(if possible).

**Make sure you have java installed on your machine**

download link: https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html
> IF YOU ARE FACING ANY PROBLEMS, PLEASE RE-DOWNLOAD, THE ISSUE MIGHT HAVE BEEN SOLVED IN LATER RELEASES
# Running executable

1. Download the repo ZIP
2. Chrome compatibility:  
    The chromedriver used is dependent on your os and chrome browser version.
    Check here and download accordingly:
    https://chromedriver.chromium.org/downloads  
    After downloading, paste the executable and overwrite(if any) in the `drivers` folder.
3. Go into the root directory of the project and run from terminal/cmd
    - For **downloading** the station data  
    run `java -jar PS2_FormFiller-1.0-SNAPSHOT-jar-with-dependencies.jar --fetch <username> <password>`
    - It will be saved in `data` folder. 
    - Just bulk sort/filter the downloaded csv file in Excel, with a few manual rearrangements if needed, and the next step will fill the form in this order.
    - **IMP** : After editing the csv in Excel **DONT SAVE AS XLSX**. Only save as CSV as it messes up with the format and will give you an error.
    - **IMP** : Before running the upload part please re-download the jar file(if you have downloaded on or before 18th Nov) as it has some minor improvements and fetch again because new stations have been added.
    - To **fill the form** from your edited sheet  
    run `java -jar PS2_FormFiller-1.0-SNAPSHOT-jar-with-dependencies.jar --upload <username> <password>  <path to modified pref sheet>`
    - Then save your preferences.
        - **Older versions**: You might get an exception at the end of the swapping. Please ignore and proceed by manually saving all the preferences.
    - NOTE: After running the script please manually check if there are minor discrepancies
    because there is faulty data in the psd website.

For Windows(in case you are facing difficulties):

![how to open cmd](./img/file_explorer.PNG)

`how to open cmd`

![cmd example](./img/command_prompt.png)

`cmd example`

## Minor Issues
- Also, set permissions for the csv file while filling form. Might give access denied error. Edit from the properties->security tab or try placing the file elsewhere(for e.g. Desktop).
- Some PS stations have their stipend/location data exchanged(website's fault). So when sorted wrt stipend/location, please manually sort them out.
# Building from source

1. Fork/clone the repo
2. Setup Maven
    - Download https://maven.apache.org/download.cgi 
    - Install maven https://www.javahelps.com/2017/10/install-apache-maven-on-linux.html (linux)
    https://www.mkyong.com/maven/how-to-install-maven-in-windows/ (windows)
3. cd into project repo root
4. run `mvn clean compile assembly:single`
