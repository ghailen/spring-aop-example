# spring-aop-example
![image](https://github.com/user-attachments/assets/7568e4a3-f6b0-4d08-a166-256616de79f9)

First we need to add this spring aop dependancy:
![image](https://github.com/user-attachments/assets/018ec462-4c86-4a80-ab9b-bd964063ab8a)
![image](https://github.com/user-attachments/assets/8431baa8-0074-47a0-8cd6-e2641b32b0cf)
Aspect annotation , it s like a servlet filters , spring interceptors.
![image](https://github.com/user-attachments/assets/cd882d21-1adb-42ba-9a24-588f9f4b0f34)

![image](https://github.com/user-attachments/assets/95df10c7-69a8-44ea-a82a-3acc5a0abdeb)

![image](https://github.com/user-attachments/assets/c36ca709-c339-4894-8d30-5d9bd786d54e)

now we have this controller class which help us to save or find by id an employee:
![image](https://github.com/user-attachments/assets/80507a1a-341c-4ff2-a34f-e3ecbbef5871)

now after eeach save or findByid we want to log .
we will create a aspect for logging.
first we create a pointcut
![image](https://github.com/user-attachments/assets/a4ec5816-aba1-4292-b294-479b1cc40398)

the first * mean any readen type in this package .
then the next * is for any class in the package , and the third one is for any method in the package , 
for the (..) mean 0 args to many arguements 

now let s create the advice:
let's add forst slf4j log.
![image](https://github.com/user-attachments/assets/5b735dbf-fd88-4fa0-96de-c695488eddf9)

1 ) this advice method will be executed before the pointcut.
2 ) this advice method will be executed after the pointcut.

dont forget to add @Component in the top of the class aspectj
lets run the postman api:
![image](https://github.com/user-attachments/assets/d9be441f-ce9c-4f25-8413-5365f6d679da)


as we can see the two advice are executed :
![image](https://github.com/user-attachments/assets/1934122f-2dbe-4cc0-8bca-c403a24a3851)
this is the signature:
![image](https://github.com/user-attachments/assets/a841a359-8c3b-4699-8957-2e40f1d9b181)

Now let s create two advices :
afterThrowing and afterReturning and comment the other advices:
![image](https://github.com/user-attachments/assets/f7fa2e9f-08ba-4d90-ab28-010d3ac6ac69)

and let s  modify the service to throw an exception if the employee id is not exist:
![image](https://github.com/user-attachments/assets/e4f0c556-f6a4-46df-b436-23afca29401a)
![image](https://github.com/user-attachments/assets/bfbeda79-aa8d-4033-880e-fe06ff017243)

now let s run for the afterReturning:
![image](https://github.com/user-attachments/assets/3207982e-02e9-4439-87f0-ef5fe5f7fee7)

![image](https://github.com/user-attachments/assets/c16c08f4-48a2-47c8-9224-61da96d0faee)
now let s run for the afterThrowing:
the employee 2 does not exist so an exception will be throwed:
![image](https://github.com/user-attachments/assets/6be71b1b-0393-4add-a34a-ce73ae64e456)

![image](https://github.com/user-attachments/assets/40857c1a-2d32-4bd7-914a-6ec4dff1c855)

now let s comment all the other code (the other advices) and create another one named around which proceed a pointcut and return an object. it will be executed before and after method.
and we will check if the object is instance of departement or an instance of employee:
![image](https://github.com/user-attachments/assets/6e579afd-1808-425c-be5d-3e931468c7f9)

let s push this :
![image](https://github.com/user-attachments/assets/546379a7-b1a8-4ae9-84c7-2e268e8063d8)

result : 
![image](https://github.com/user-attachments/assets/bbbfe8b3-e3da-4295-93bd-6b4b880cfde0)

let s change signature with args:
![image](https://github.com/user-attachments/assets/f71c40a9-4f06-4d58-909f-f4e378d4feb3)
and run the api again:
![image](https://github.com/user-attachments/assets/ceceef23-fd75-4229-bcf7-cc0a0aca6216)

and now we can see the request and the response:
![image](https://github.com/user-attachments/assets/b4f5dcd8-2392-4677-b85c-be7ccfdbdda3)
before the id is 0 and after the id is one .

now let s modify the pointcut , we will change execution by within , and put the classes in the service package (as we can see the expression is changed )
![image](https://github.com/user-attachments/assets/8a68d149-98c9-41a6-b60a-92d39e7b2397)
let s restart the application then run the postman:
![image](https://github.com/user-attachments/assets/b3186201-cede-42fc-941e-c5e438ef195b)
=>
![image](https://github.com/user-attachments/assets/e7713627-4f35-418e-80ff-7ed824044bb9)
and for the departementt api :
![image](https://github.com/user-attachments/assets/d4b20066-6c91-4483-b3cf-e84a7df3144a)
=> resquest and response in the console is working fine
![image](https://github.com/user-attachments/assets/8f29d207-544c-4ec6-9626-3796f33e50d6)

if you want to execute for sub package of springaop you need to use .
![image](https://github.com/user-attachments/assets/23ed0543-807d-4b42-a080-53a23d215775)
if you want to execute only for departement service:
![image](https://github.com/user-attachments/assets/e2ecd54e-026d-413a-a5a3-5ab3f27a7b17)

Now if you want to use pointcut for a custom annotation:
create a custom annotation:
![image](https://github.com/user-attachments/assets/bd71e1bd-cf44-4ee7-808e-956a8ddcdeda)
![image](https://github.com/user-attachments/assets/efb75ab4-6f63-439d-b9e6-77bd618cf254)

![image](https://github.com/user-attachments/assets/a51cb381-cd48-42e6-bd8d-4fe52035966f)



