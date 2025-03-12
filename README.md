<h1>Python Port Scanner</h1>

<h2>Description</h2>

<br />


<h2>Languages and Utilities Used</h2>

- <b>PyCharm Community Edition (Python IDE)</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b>

<h2>Code walk-through:</h2>

<p align="center">
<br />
<br />
The Complete Code:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/FullCode.jpeg?raw=true" height="200%" width="200%"/> <br />
<br />
<br />
<br />
<br />
<h3>Imports and Global Variables:</h3>
Lines 1-11:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L1.PNG?raw=true" height="80%" width="80%"/> <br />
Lines 1 through 4 import necessary modules: "sys" for system operations, "socket" for network communication, "datetime" for handling date and time, and "threading" for enabling concurrent execution of the code through the use of threads. Lines 6 through 11 define global variables used throughout the program. Lines 6, 7, and 8 define and store default values for key parameters: the maximum number of threads allowed, the connection timeout duration, and the range of ports to be scanned, assigning them to their respective variables. Lines 10 and 11 create a semaphore, which controls access to a limited resource; in this case, it limits the number of concurrent threads to 200, and a thread lock, which ensures that only one thread can print to the console at a time, preventing overlapping or mixed output.<br />
<br />
<br />
<h3>Defining the "scan_port" Function:</h3>
<p/>
