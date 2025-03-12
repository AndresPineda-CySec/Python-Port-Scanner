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
<h3 align="center">Imports and Global Variables:</h3>
<p align="center">
Lines 1-11:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L1.PNG?raw=true" height="80%" width="80%"/> <br />
Lines 1 through 4 import necessary modules: "sys" for system operations, "socket" for network communication, "datetime" for handling date and time, and "threading" for enabling concurrent execution of the code through the use of threads. Lines 6 through 11 define global variables used throughout the program. Lines 6, 7, and 8 define and store default values for key parameters: the maximum number of threads allowed, the connection timeout duration, and the range of ports to be scanned, assigning them to their respective variables. Lines 10 and 11 create a semaphore, which controls access to a limited resource; in this case, it limits the number of concurrent threads to 200, and a thread lock, which ensures that only one thread can print to the console at a time, preventing overlapping or mixed output.<br />
<br />
<br />
<h3 align="center">Defining the "scan_port" Function:</h3>
<p align="center">
Lines 13-26:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L13.PNG?raw=true" height="80%" width="80%"/> <br />
This block of code creates a function named "scan_port" that passes three arguments, target, port, and timeout, and acquires the sephamore to control concurrent thread execution. Lines 15 through 22 make up a "try" block, which creates a TCP socket, sets a timeout, and attempts to connect to the specified target IP. If the connection succeeds, it prints the result and closes the socket. If errors occur, they are ignored by the "except" block: lines 23 and 24. The function ends with the "finally" block, which releases the semaphore to prevent freezing of the threads at lines 25 and 26.<br />
<br />
<br />
<h3 align="center">Defining the "main" Function:</h3>
<p align="center">
Lines 29-40<be />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L29.PNG?raw=true" height="80%" width="80%"/> <br />
This is the start of the "main" function. Line 29 defines the function as "main," and lines 30-34 introduce the user to the port scanner and offer two versions of the scanner to experience: Default and Custom. If the user runs the scanner in the default mode, the program will use the default time out, thread count, and port range.<br />
<br />
<br />
Lines 40-59<be />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L40.PNG?raw=true" width="80%"/> <br />

</p>
