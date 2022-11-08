>>frankolious> npx create-next-app --tx

#root domain stuff to scaffold a typescript project

#Rules for .gitignore
>Here are the general rules for matching patterns in .gitignore files: 

##Pattern	Explanation/Matches	Examples
 	Blank lines are ignored	 
# text comment	Lines starting with # are ignored	 
name	
All name files, name folders, and files and folders in any name folder	/name.log
/name/file.txt
/lib/name.log
name/	Ending with / specifies the pattern is for a folder. Matches all files and folders in any name folder	/name/file.txt
/name/log/name.log

no match:
/name.log
name.file	All files with the name.file	/name.file
/lib/name.file
/name.file	Starting with / specifies the pattern matches only files in the root folder	/name.file

no match:
/lib/name.file
lib/name.file	Patterns specifiing files in specific folders are always realative to root (even if you do not start with / )	/lib/name.file

no match:
name.file
/test/lib/name.file
**/lib/name.file	Starting with ** before / specifies that it matches any folder in the repository. Not just on root.	/lib/name.file
/test/lib/name.file
**/name	All name folders, and files and folders in any name folder	/name/log.file
/lib/name/log.file
/name/lib/log.file
/lib/**/name	All name folders, and files and folders in any name folder within the lib folder.	/lib/name/log.file
/lib/test/name/log.file
/lib/test/ver1/name/log.file

no match:
/name/log.file
*.file	All files withe .file extention	/name.file
/lib/name.file
*name/	All folders ending with name	/lastname/log.file
/firstname/log.file
name?.file	? matches a single non-specific character	/names.file
/name1.file

no match:
/names1.file
name[a-z].file	[range] matches a single character in the specified range (in this case a character in the range of a-z, and also be numberic.)	/names.file
/nameb.file

no match:
/name1.file
name[abc].file	[set] matches a single character in the specified set of characters (in this case either a, b, or c)	/namea.file
/nameb.file

no match:
/names.file
name[!abc].file	[!set] matches a single character, except the ones spesified in the set of characters (in this case a, b, or c)	/names.file
/namex.file

no match:
/namesb.file
*.file	All files withe .file extention	/name.file
/lib/name.file
name/
!name/secret.log	! specifies a negation or exception. Matches all files and folders in any name folder, except name/secret.log	/name/file.txt
/name/log/name.log

no match:
/name/secret.log
*.file
!name.file	! specifies a negation or exception. All files withe .file extention, except name.file	/log.file
/lastname.file

no match:
/name.file
*.file
!name/*.file
junk.*	Adding new patterns after a negation will re-ignore a previous negated file
All files withe .file extention, except the ones in name folder. Unless the file name is junk	/log.file
/name/log.file

no match:
/name/junk.file
