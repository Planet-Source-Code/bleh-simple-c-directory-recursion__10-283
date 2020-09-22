<div align="center">

## Simple C\# Directory Recursion


</div>

### Description

This shows and explains how to recursivley add all files, folders, and subfolder to an ArrayList.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[bleh](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bleh.md)
**Level**          |Beginner
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |C\#
**Category**       |[Files](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files__10-2.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bleh-simple-c-directory-recursion__10-283/archive/master.zip)





### Source Code

<font face="Verdana" size="2">
<div align="center"><b>Simple Directory Recursion</b></div>
<p><b>Introduction:</b><br>One of the things I liked a lot back when I was a VB programmer was the easy directory recursion using the File System Object, a function I use quite a bit in my applications. It became a bit more complex in Delphi (at least, the way I do it), so since I am now learning C#, I figured it would be wise of me to figure it out yet again. I was surprised about how simple it is
in C#.</p>
<b>The Code:</b><hr size="1" color="#000000" width="100%">
<pre><font size="2">
using System.IO;
...
<font face="verdana" size="1" color="green">// This will be our ArrayList that everything is stored in.</font>
ArrayList sFileList = new ArrayList();
private void recurseDirs(string sPath)
{
	<font face="Verdana" size="1" color="#008000">// First we create an instance of DirectoryInfo and point it to the path we passed as a parameter to the function</font>
	DirectoryInfo dirInfo = new DirectoryInfo(sPath);
	<font face="verdana" size="1" color="green">// Next, we are adding all files in the current path to the ArrayList.</font>
	sFileList.AddRange(dirInfo.GetFiles());
	<font face="verdana" size="1" color="green">// Now we step through all of the directories in dirInfo, add them to the ArrayList, and then call the function again.</font>
	foreach(DirectoryInfo subDirs in dirInfo.GetDirectories())
	{
	  sFileList.Add(subDirs.FullName);
	  recurseDirs(subDirs.FullName);
	}
}
</font></pre>
<p><b>Using This Code:</b><hr size="1" color="#000000" width="100%">
As shown in the code, make sure to add <b>System.IO</b> to your namespaces. To call this function from your code, simply type <br><br> <i>recurseDirs("C:\\Whatever\\Path\\Here\\");</i></p>
<p><b>In Conculsion:</b><hr size="1" color="#000000" width="100%">
Obviously, adding everything to an ArrayList is just an example of what to do with the information. I did notice that it will add all temporary, hidden, and system files and folders to the list. There is a workaround for this using FileAttributes, but since I am still a C# beginner, I haven't figured it out yet.
</font>

