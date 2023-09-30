<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.719 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Sat Sep 30 2023 13:44:50 GMT-0700 (PDT)
* Source doc: File permissions in Linux
----->



# File permissions in Linux


## Project description

The research team at my organization needs me to ensure users on this team are authorized with the appropriate permissions. The permissions do not currently reflect the accurate level of authorization that should be given for certain files and directories. Modifying the permissions to the appropriate level will help keep the system secure. This endeavor was performed though the following tasks:  


## Check file and directory details

The following code block shows how I use Linux commands to evaluate the existing permissions relating to a specific directory in the file system.

The first line of code displays the command I entered, and the remaining lines display the output. The _ls _command with the _-la_ option displays permissions to files and directories, including hidden files. The output of my command indicates that there is one subdirectory named _drafts_, one hidden file named <code><em>.project_x.txt</em></code>, and four other project files. The 10-character string in the far left column represents the permissions set on each file or directory. 


## Describe the permissions string

The 10-character string can be broken down to determine who is authorized to access the file or directory and their specific permissions. The characters and what they represent are explained below: 



* **1st Character:** Indicates file type. The letter d is for directory and a hyphen (-) is for a regular file.
* **2nd-4th Characters: **These characters indicate read (r), write (w), and execute (x) permissions for the user. The user is the owner of the file. When one of these characters is a hyphen (-) instead, it indicates this permission is not granted to the user. 
* **5th-7th Characters: **These characters indicate read (r), write (w), and execute (x) permissions for the group. A group consists of several users. When one of these characters is a hyphen (-) instead, it indicates this permission is not granted to the group.
* **8th-10th Characters: **These characters indicate read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, it indicates this permission is not granted for other. 

For example, the file permissions for project_m.txt are  -rw-r-----. The first character indicates that project_m.txt is a file since it is a hyphen (-). The second and fifth characters are r, which indicates that user and group have read permissions. The third character has a w, which indicates that only the user has write permission. No type of owner has execute permissions for project_m.txt. 


## Change file permissions

The organization does not allow other to have write access to any files. To adhere to this, I referred to the file permissions that were previously displayed in the shell. I found that project_k.txt needs to have the write access removed for other. The following code demonstrates how I used Linux commands to do this: 

The chmod command in the first line of code changes the permissions on files and directories. The first argument indicates the permissions that will be changed, and the second argument indicates the file or directory. In this case, the write permission was removed from other for the project_k.txt file. I used ls -la to ensure my update was processed. 


## Change file permissions on a hidden file

The research team has archived .project_x.txt, which is why it’s a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. The following code demonstrates how I used Linux commands to change the permissions: 

In this example I used chmod to set the permissions of user and group to read only. The equal (=) sign sets the permissions exactly as specified and overwrites existing permissions. 


## Change directory permissions

The files and directories in the projects directory belong to the researcher2 user. Only researcher2 should be allowed to access the drafts directory and its contents. The following code demonstrates how I used Linux commands to change the permissions: 

Since the group had execute permissions, I used chmod to remove them. The researcher2 user already had all the necessary permissions. 


## Summary

[Add content here.]
