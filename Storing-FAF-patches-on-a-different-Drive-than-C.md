FAF stores its patch files, movies etc in *C:\\ProgramData\\FAForever\\*
and the installer doesn't give you the option to choose a different
directory for that. If you use windows you have the option of using a
NTFS junction to save space on your C drive.

1.  Cut out the entire FAForever folder from C:\\ProgramData\\ and put
    it on a drive with more space. As example we'll use *D:\\*
2.  Open the command prompt (windows + R -> cmd -> enter)
3.  Use the command *mklink /j C:\\ProgramData\\FAForever D:\\FAForever*
    to create a junction