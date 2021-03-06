
<p>You may want to share the game programs you make with other people. Having other people play your games is a great way to show off your skills. However, they may not have Python installed on their computer. There is a way to run Python programs without installing the Python interpreter: You will have to compile your .py script into a .exe executable program.</p>

<p>Compiling source code means converting that source code into machine language, which is the programming language your computer understands. Programming in machine language is very long and tedious, and higher-level languages such as Python make programming easier.</p>

<p>This appendix will show you how to compile your .py Python files into .exe programs that can be run on Windows without having Python installed.</p>


<h3>Step 1: Download and Install py2exe</h3>


<p>First, you will need to download and install a module called py2exe from <a href='http://sourceforge.net/projects/py2exe/files/'>http://sourceforge.net/projects/py2exe/files/</a>. Be sure to download the correct version of py2exe for your version of Python. (For example, download py2exe-0.6.9.win32-py2.6.exe if you have installed Python 2.6 on your computer.)</p>

<p>The py2exe module only works on 2.x versions of Python, and not Python 3. You will have to convert your programs to run on Python 2 if you have written them for Python 3. This is fairly easy. There are not many differences between Python 2 and 3, and they are documented in Appendix A of this book.</p>

<p>After downloading the py2exe installer, double click on it to install it. This installation is much like how you installed Python. Just keep clicking the Next button until you reach the end.</p>

<p>After you have installed py2exe, you can make sure that the installation was successful by running the interactive shell and typing the following:</p>


<div class='sourceblurb'>
&gt;&gt;&gt; import py2exe<br />
&gt;&gt;&gt;<br />
</div>


<p>If you do not see anything, then the installation was successful. If you see this error:</p>


<div class='sourceblurb'>
&gt;&gt;&gt; import py2exe<br />
>>> import py2exe<br />
Traceback (most recent call last):<br />
&nbsp;&nbsp;File "&lt;stdin&gt;", line 1, in ?<br />
ImportError: No module named py2exe<br />
&gt;&gt;&gt;<br />
</div>


<h3>Step 2: Create Your setup.py Script</h3>


<p>After you have installed py2exe and confirmed that it is installed, you will need to create a Python program with the name setup.py. The contents of this program should be as follows:</p>


<div class='sourceblurb'>
from distutils.core import setup<br />
import py2exe<br />
setup(console=['hello.py'])<br />
</div>


<p>Replace hello.py in the source code above with the filename of the Python program you want to compile. Be sure to save the setup.py in the same folder as the Python program you want to compile (that is, hello.py, or whatever the filename is).</p>


<h3>Step 3: Run Your setup.py Script</h3>


<p>Next, you will have to run your setup.py with a command line option. You cannot run setup.py from IDLE by pushing the F5 key or selecting Run Module from the Run menu. You must use the Windows command line.</p>

<p>To start the Windows command line, click on the Start button in the bottom left corner and select "Run". In the windows that opens, type "cmd" and click OK.</p>

<p>A black window with text should appear. Type "<span class='m'>cd c:\Python26</span>" (or the folder that you have saved your programs to) to change folders to the folder containing your Python script and setup.py. From that folder, type "<span class='m'>c:\Python26\python.exe setup.py py2exe</span>". The first part (<span class='m'>c:\Python26\python.exe</span>) runs the Python interpreter from the command line. The first command line option (<span class='m'>setup.py</span>) is the script that the interpreter should run. The second command line option (<span class='m'>py2exe</span>) tells the script to run with the py2exe option.</p>

<p>There will be a large amount of text from running this program. You can ignore this text.</p>

<p>When the compilation is finished, there will be two new folders, named build and dist. You can delete the build folder because it only contains files that were used during compilation. The dist folder contains all the files you want to give to other people, including the hello.exe binary executable. (Your executable may have a different name. If your setup.py had hello.py, then compilation produces a program named hello.exe.)</p>



<h3>Step 4: Distribute Your Program</h3>


<p>It's not easy to email all the files in the dist folder to someone. You can use a "zip program" to package these many files into one file (called a zip file because it has the extension .zip). Zip programs can be downloaded from the Internet for free. Some popular, free zip programs are 7-zip from <a href='http://www.7-zip.org/download.html'>http://www.7-zip.org/download.html</a> or WinRAR from <a href='http://www.rarlab.com/download.htm'>http://www.rarlab.com/download.htm</a>.</p>

<p>You can rename the dist folder to something else if you wish. The files simply have to be in the same directory.</p>

<!-- Page break inserted for CreateSpace printing layout prettifying: -->

<h3>Summary</h3>


<p>The process for turning your .py Python scripts into .exe binary executable programs for Windows is simple:</p>


<p>Step 1: Download and install py2exe from <a href='http://sourceforge.net/projects/py2exe/files/'>http://sourceforge.net/projects/py2exe/files/</a></p>

<p>Step 2: Create a setup.py file that looks like this:</p>


<div class='sourceblurb'>
from distutils.core import setup<br />
import py2exe<br />
setup(console=['hello.py'])<br />
</div>


<p>Step 3: Run "<span class='m'>c:\Python26\python.exe setup.py py2exe</span>"</p>

<p>Step 4: Package up the dist folder into a zip file.</p>

<!-- Chapter Navigation Links -->

</body>
</html>
