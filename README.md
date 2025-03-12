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
Lines 1 through 4 import necessary modules: "sys" for system operations, "socket" for network communication, "datetime" for handling date and time, and "threading" for enabling concurrent execution of the code through the use of threads. Lines 6 through 11 define global variables used throughout the program. Lines 6, 7, and 8 define and store default values for key parameters: the maximum number of threads allowed (DEFAULT_MAX_THREADS), the connection timeout duration (DEFAULT_TIMEOUT), and the range of ports to be scanned (DEFAULT_PORT_RANGE), assigning them to their respective variables. Lines 10 and 11 create a semaphore, which controls access to a limited resource; in this case, it limits the number of concurrent threads to 200, and a thread lock, which ensures that only one thread can print to the console at a time, preventing overlapping or mixed output.<br />
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
Lines 29-40:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L29.PNG?raw=true" height="80%" width="80%"/> <br />
This is the start of the "main" function. Line 29 defines the function as "main," and lines 30-34 introduce the user to the port scanner and offer two versions of the scanner to experience: "Default" and "Custom." If the user runs the scanner in the default mode, the program will use the default time out, thread count, and port range.<br />
<br />
<br />
Lines 40-59:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L40.PNG?raw=true" height="100%" width="100%"/> <br />
If the user selects the "Custom" option when running the scanner, they can customize certain aspects of the program, such as the port range. This code block handles the determination of the port range. Line 44 allows the user to use either a custom or default port range (1-65535). The entire if-statement spans from lines 45 through 65, but for now, I will focus on the section that executes when the user chooses "Custom," which initiates the try block. Lines 48 and 49 prompt the user to input the start and end of the port range. Lines 50 through 58 perform input validation and error handling to ensure the user enters valid data types and values.<br />
<br />
<br />
Lines 60-65:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L60.PNG?raw=true" height="60%" width="60%"/> <br />
This block of code is the rest of the if-statement. If the user selects not to use a custom port scan, the port range is set to the global variable "DEFAULT_PORT_RANGE." Lines 63 through 65 are input validation.<br />
<br />
<br />
Lines 67-80:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L67.PNG?raw=true" height="100%" width="100%"/> <br />
This code block sets the "timeout" duration, specifying how long the program will attempt to connect to a port before terminating the attempt. The user can select a timeout value between 0.1 and 2 seconds. Additionally, lines 73 through 80 are dedicated to error handling and input validation, ensuring reliable operation.
<br />
<br />
Lines 82-95:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L82.PNG?raw=true" height="100%" width="100%"/> <br />
This block is essentially written the same as the previous one but determines the maximum thread count, which defines the number of concurrent threads the program can run at a given time.
<br />
<br />
Lines 97-102:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L97.PNG?raw=true" height="60%" width="60%"/> <br />
This code block handles user input validation and exits the program if the input is invalid. Line 100 asks for input from the user to determine the target IP that the port scanner will scan and line 102 limits the number of concurrent threads to the variable "max_threads," preventing excessive resource usage.
<br />
<br />
<h3 align="center">Executing the Port Scan:</h3>
<p align="center">
Lines 105-127:<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/L105.PNG?raw=true" height="100%" width="100%"/> <br />
<br />
<br />
<h3 align="center">Results of a Default Scan:</h3>
<p align="center">
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/ra1.PNG?raw=true" height="40%" width="40%"/> <br />
Whenever the script first starts, the user is prompted to select a "Default" or "Custom" scan by typing the number 1 or 2. To select run a default scan, the number 1 is typed.<br />
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/ra2.PNG?raw=true" height="40%" width="40%"/> <br />
The next entry is the Target IP the port scanner will connect to.<br /> 
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/ra3.PNG?raw=true" height="60%" width="60%"/> <br />
Once the Target IP has been entered, the scan will start and the port scanner settings will be listed. Since this is a default scan, all of the settings are preconfigured to the defaults settings that were stored in the global variables "DEFAULT_MAX_THREADS," "DEFAULT_TIMEOUT," AND "DEFAULT_PORT_RANGE."<br />
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/ra4.PNG?raw=true" height="60%" width="60%"/> <br />
Once open ports are found, they will be listed in numerical order. Once all ports have been scanned, the program will let the user know the scan has been complete and the program will terminate.<br />
<br />
<br />
<br />
<br />
<h3 align="center">Results of a Custom Scan:</h3>
<p align="center">
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb1.PNG?raw=true" height="40%" width="40%"/> <br />
This time I will cover a "Custom" scan by typing "2."
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb2.PNG?raw=true" height="60%" width="60%"/> <br />
Now that I am running the scan as "custom," We gain the freedom to customize the settings that control the way the scan behaves. The first choice offered by the program is if I would like to specify a port range. If I type "n," the default port range will be used. I type "y," which allowsme to specify a start and and end to my port range.<br />
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb3.PNG?raw=true" height="60%" width="60%"/> <br />
Here I choose the port range to start at port 5,000 and end at port 50,000.<br />
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb4.PNG?raw=true" height="100%" width="100%"/> <br />
The next prompt asks the user to enter a timeout. For this scan, since I am scannning a local host on my network, I choose to do the fastes timeout available to save time: 0.1.<br />
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb5.PNG?raw=true" height="100%" width="100%"/> <br />
I am now given the option to choose the max thread count. Once again I choose a value to save time: 2000. This is the highest thread count available, and also the most cpu intensive.<br /> 
<br />
<br />
<img src="https://github.com/AndresPineda-CySec/Python-Port-Scanner/blob/main/images/rb6.PNG?raw=true" height="60%" width="60%"/> <br />

<br />
<br />
This concludes the steps I took to complete my PowerShell Incident Response Script.<br />
</p>
