#    
##  :::: :::: :::: ::::
##  Welcome to my command tips and tricks 

    Commands usually work with the command say: ls (parameter one)-a(parameter two)

## Navigating and File Managment
    * We usally like to see what information we can see. There are two things I like to see when looking at a command line. What directory I'm in and what files are in that directory. The first thing we see is what directory we are in c:/projects.  
    The second thing I love to see is using ls. ls view's all the files in the directory.  

    Navigation commands  
       
        (View All Files)  
       - ls -a  
  
        (Move back a folder)  
       - cd ..  

        (Move to route)  
        or any folder just add the full directory cd c:/projects
       - cd /  

        (Search for anything)  
        grep can be used to search for lines of code in a file  
        or files in a directory  
       - grep -E ".*" filename  

        (Creating folder)  
       - mkdir your_directory_name_here  
    


## Processing Text and Manipulation

    * We can use the head command to view the top of a file to see what it contains. Here we use the head command with -20 as parameter one to indicate the first 20 lines (you can change to 100, 10, any amount of lines. 
    our second parameter is our file we are viewing. pom.xml
      
        head -20 pom.xml 


    * when working with lots of lines of code and you want to get rid of duplicate lines of code we can use  

        uniq  

    * if you need to sort lines of text 

        sort  

    * if you have a command and would like the output of that command to goto a txt or other file we can use 

        your_command > output.csv

    *    

## Command Line Efficiency

## System Monitoring and Management 

## Scriping and Automation


## Merging Code
1. git checkout release/ee-CURRENTRELEASE          -----Note pom version number 
2. git pull
3. git checkout release/ee-OLDRELEASE                    -----Note pom version number 
4. git pull
5. git checkout -b feature/pomUpdate_OLDPOMVERSION_MONTHDAY 
6. ./build_scripts/pom-update-versions.sh OLDPOMVERSION NEWPOMVERSION 
	 - git status
    - git clean -df
7. git add * 
8. git commit -m "pom update from OLDRELEASE to CURRENTRELEASE" 
9. git checkout release/ee-CURRENTRELEASE 
10. git checkout -b feature/LVL_merge_fromOLDPOMVERSION_to_NEWPOMVERSION_MONTHDAY 
11. git merge feature/pomUpdate_OLDPOMVERSION_MONTHDAY 
12. git mergetool (Only need to run this if there are conflicts)
13. git commit -m "resolved merge conflicts from OLDRELEASE to CURRENTRELEASE" (Only need to run if you had merge conflicts)
14. git push
