# cldup
CLean up DUPlicate files
* **Efficient:**  Using database maintained increasingly.
* **Reliable:**  MD5 compared before reporting/removing duplicate file.

cldup is a bash CML script that finds out/cleans up duplicate files. It creates a database of all the files, and identifies duplicate files base on the pre-scanned database.


Using Steps
1. Download the file cldup and make it executable:

          chmod +x cldup
   
2. Edit the the configurations at the top of cldup
    ```shell
    #1.DIR(s) to be covered
    BASEDIR=('/volume1')  #The base of the dir tree be scanned for duplicate files. Change it to your dir. The default is for synology NAS volume1. More than one dir can be added as ('/volume1' '/volumen2')
    
    #2.PATH NAME of the database file
    FILE_LIST_DB=~/.allfiles.n.db  #specify the name of database file. The default name is OK for most of users. 
    ```     
3. Run with -u option to create the database. It will take a few minutes to hours, depends on the volume of your files.

          cldup -u

4. Once the database was created, you can :
  >> use -l options to check if a file is a duplicate one.

         cldup -l IMG_3456.JPG
         cldup -l *
     
  >> use cldup to clean up (delete with prompt) duplicate files.
  
          cldup IMG_3456.JPG
          cldup *
  
  >> use cldup -f * to clean up files quickly(delete duplicate files with out prompt).

          cldup -f *.JPG
    
  >> use cldup -u to update the database increasingly at anytime.
  
          cldup -u
    
  >> sure you can maintain the database and clean up a dir with single command.
  
          cldup -uf *
        
