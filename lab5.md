In lab report 3 we were asked to choose one command and find 4 new ways to use them. I decided to use the grep command and I found 4 alternate ways to use the grep command. The first alternate way I found to use grep was. ``grep -rl "word`` this command searches recursively and lists all the files that contain the word frightening. The second alternate way I found to use grep was `` grep -n "word FileName`` This command lists the line number of where a specific word exists in a file. The output shows the line number first and then the entire line listed out for you. The third alternate way I found to use grep was ``grep -v "word" FileName`` This command looks throuh the file for a particular word and it inverts it so that all the lines that do not contain the word are returned instead. The final alterate way I found to use grep was `` grep -E '[character range]{# of characters}' FileName``. This method looks for a specific character range in the words and the number of characters allowed and returned all the lines that contain instances that pass the conditions. 

4 alternates ways to use the find command are:


``
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/docsearch (main)
$ find written_2 *txt f mtime +30 -exec rm {} \;
rm: cannot remove 'written_2': Is a directory
rm: cannot remove 'written_2/non-fiction': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Abernathy': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Berk': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Castro': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Fletcher': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Kauffman': Is a directory
rm: cannot remove 'written_2/non-fiction/OUP/Rybczynski': Is a directory
rm: cannot remove 'written_2/travel_guides': Is a directory
rm: cannot remove 'written_2/travel_guides/berlitz1': Is a directory
rm: cannot remove 'written_2/travel_guides/berlitz2': Is a directory ``

 
This method find the number of text files in a directory that are edited within 30 days and removes them. The command can be adjusted to remove differne types of files by chaning the txt part. It can also be adjusted to have a different time frame instead of 30 days. This method removed all the files in the written 2 directory because I just cloned the directory so all the files would be edited within 30 days. 

``
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/docsearch (main)
$ find written_2/ -type f -mtime -7
``

This method finds the number of text files in a directory within 7 days. The command can be adjusted to find files edited in different time frames. In this case the return was nothing since the directory was empty from our previous command. 

``
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/docsearch (main)
$ find written_2/ -empty
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
``
This method returns the number of empty directories. This command returned all the directories in the written_2 direcotry because all the directories had their text files removed from the previous command. 

``
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/docsearch (main)
$ find written_2 -type d -empty -delete
``
This mehtod removes all the empty directories. This can be very useful to make sure directories that are empty are properly removed. In this case all the empty directories of written_2 were removed. 

``
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/docsearch/docsearch (main)
$ find written_2 -type f -size +1024c -size -2048c
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
``
This mehtod finds the number of files of type f in a given directory that are within a specific size range. In this case I re-cloned the directory so it contains the files it originally contained. The range was 1024c to 2048c and the output was as follows. 

``
less /path/to/compressed/file.gz
``
This is another very useful method that allows someone to view the contents of a compressed file without extracting it. 

``
less -N /path/to/file
``
This mehtod would open the file and keep line numbers while viewing it. 



