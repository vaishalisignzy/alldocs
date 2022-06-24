# Previous Fixed Issues

### 1. CRLF Injection&#x20;

It was possible to add Carriage Return and Line Feed characters in the GET Parameter to Set the value of cookies and also html content in the page itself. The following issue was fixed on **25 May 2018**

### **2. Reflected Cross Site Scripting**

It was possible to add special characters into the URL and add custom JavaScript code into the URL and because of which the Reflected Cross Site Scripting was possible , this issue was fixed in **25 May 2018**

### 3. Template Injection&#x20;

It was possible to add \{{2 \* 2\}} in the URL to respond it with 4 which confirmed Template Injection , This issue was fixed on **25 May 2018.**

### 4. JavaScript Injection&#x20;

It was possible to inject JavaScript into URL parameters to delay the server respond time. This issue was fixed on **25 May 2018**

### **5. NoSQL Injection**&#x20;

NoSQL injection was possible on the URL parameter, which resulted in leaking database of web server. This issue was fixed on **25 May 2018.**

### **6. Local File Inclusion**&#x20;

This vulnerability occurred on the path manipulation, of the patron ID because of which it was easy enough to read out contents of any web server files like /etc/passwd/ , /etc/shadow. This issue was fixed on **25 May 2018**

### 7. Open Redirect

URL redirection was possible due to certain parameters in the URL, because of which it was possible to steal authentication token via referer header. This issue was fixed on **25 May 2018**

### 8. Payment Tampering due to HTTP Parameter Pollution&#x20;

This bug was disclosed in one of our APIs when a user is prompted to send some cash to another user,  The process was being executed via JSON, it was possible to add extra **"cash" : "new\_value"** parameter in JSON request to change the value of cash sent. This issue was fixed on **25 May 2018.**

### **9. Stored Cross Site Scripting**&#x20;

As special characters were not being sanitised, it was possible to inject JavaScript code into the name parameters and save the same and because of which the JavaScript code was running on the server, as the name parameter was getting saved in the database it confirmed our case for Stored Cross Site Scripting. This issue was fixed on **25 May 2018.**



****
