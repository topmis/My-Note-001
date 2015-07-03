```
#搜尋2001年5月28日11時59分到2001年5月29日0時10分間所有的檔案  
touch -t 200105281159 file1 
touch -t 200105290010 file2 
fine . -newer file1 ! -newer file2 -print  
如此就會搜尋出數個檔案 扣除file2的就是所得...
```
```
find . –name checklist –print 
找出所有在當前目錄下檔名為checklist的檔案並顯示出來。 
```
```
find /usr –name \'v*[0-9]\' –print 
找出所有在/usr目錄下檔名為v開頭0-9之一結尾的檔案並顯示出來。 
```
```
find /usr –size +1000 –print 
找出所有在/usr目錄下檔案大小大於1000個blocks(512 bytes)的檔案並顯示出來。（-1000為小於） 
```
```
find /usr –mtime –1 –print 
找出所有在/usr目錄最近一天內被修改的檔案並顯示出來。（+1為比1天更舊的檔案） 
```
```
find / -name core –exec rm {} \\\\; 
找出所有在根目錄下檔名為core的檔案並刪除掉。（-exec 後放欲執行之命令與參數，最後以 \\\\; 結尾，{}表find所找到的檔名。 

find /ice/share12 -name \'*.mp3\' –exec ls -lag {} \\\\; -print > mp3.txt 

find /ice/share12 -name \'*.mp3\' –ok rm {} \\\\; 
```cat 