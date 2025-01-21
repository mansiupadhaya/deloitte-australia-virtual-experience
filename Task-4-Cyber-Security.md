# Task 4 - Cyber Security

In this task, I was responsible for the investigation of an alleged breach of Daikibo's internal systems. My role involved verifying whether an attacker could access the manufacturing status dashboard from the internet and analysing log files for suspicious activities.

## Steps Taken

* Confirming Dashboard Access
  
    - Revisited the scope of the dashboard project from the previous task to confirm that the dashboard is restricted to Daikibo's intranet.
    - Verified that external access was only possible via VPN tunnelling, making a direct attack from the internet infeasible.
    - Inspecting the Log File
 
* Inspecting the Log File
    - Opened the provided web_requests.log file in VSCode for easier visual inspection
    - Analysed blocks of text, each representing activity from a unique IP address, to identify suspicious patterns
    - Followed the hints provided to spot sequences of requests, focusing on:
        Login followed by requests for dashboard resources
        Automated API requests occuring at precise intervals
      
* Idenfifying suspicious activity
      - Found a user ID exhibiting unusual behaviour
      - Regular login followed by periodic API requests without loading page resources
      - Requests were timestamped at exact hourly intervals, indicating automation rather than human activity


By utilising the task's hints provided, I was able to adopt a more systematic approach to identify the critical details about the suspicious user activity. 
