Lamda is aws serverless service. It can also be called compute service
You upload your code and create a lamda function, takes care of provisioning and managing your OS, patching and scaling.
1 event = 1 function so functions are independent. 
1 function can trigger other functions so 1 event = x functions if functions trigger other functions.
It can be event drive or compute driven.

It can support Node.Js java, python, C# and GO.

First 1 million are free. It has continous scaling but it can be prone to outage. Lamda scales out not up.

AWS X-ray allows to debug Lamda, it can also be used globally.