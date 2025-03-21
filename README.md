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
