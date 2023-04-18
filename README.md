# cldup
CLean up DUPlicated files: A bash CML script that finds out/cleans up duplicated files. It creates a database of all the files, and identifies duplicated files base on the pre-scanned database.


Using Steps
1. Download the file cldup and make it executable:

          chmod +x cldup
   
2. Edit the the configurations at the top of cldup
    ```shell
    #1.DIR(s) to be covered
    BASEDIR='/volume1'  #The base of the dir tree be scanned for duplicated files. Change it to your dir. The default is for synology NAS volume1.
    
    #2.PATH NAME of the database file
    FILE_LIST_DB=~/.allfiles.n.db  #specify the name of database file. The default name is OK for most of users. 
    ```     
3. Run with -u option to create the database. It will take a few minutes to hours, depends on the volume of your files.

          cldup -u

4. Once the database was created, you can :
  use -l options to check if a file is a duplicated one.

         cldup -l IMG_3456.JPG
         cldup -l *
     
  >> use cldup to clean up (delete with prompt) duplicate files.
  
          cldup IMG_3456.JPG
          cldup *
  
  >> use cldup -f * to clean up files quickly(delete duplicated files with out prompt).

          cldup -f *.JPG
    
