# Protecting-Vulnerable-Web-Application
Utilizing a WAF to protect a vulnerable web application 

For this lab we will be utilizing 2 machines: kali linux and ubuntu server with DVWA installed. After testing different attacks on DVWA we will install our WAF and show how these attacks will now be blocked by it.

We will start with a classic XSS attack:

![xss 1](https://github.com/user-attachments/assets/00e44492-e287-4855-bb23-aaf42032c028)
![xss 2](https://github.com/user-attachments/assets/6281acc8-0ad5-4221-91af-6bec53ef63b9)

Now let's try an sqli:

![sqli](https://github.com/user-attachments/assets/fd794bf5-4843-41e8-9a08-5dd69fe4ea17)

Let's upload a php webshell for an easy access:

![php up](https://github.com/user-attachments/assets/793eeb5c-75a5-403a-afb5-6ccc69e9bc1f)
![php file upload](https://github.com/user-attachments/assets/ff09430d-0e7b-4315-9822-b8ade79ae781)

We can also do a command injection:

![command injection](https://github.com/user-attachments/assets/33d9e023-70cf-45b3-8b52-3a234b189cbb)

Path traversal is also possible on DVWA:

![path traversal](https://github.com/user-attachments/assets/897f722b-5888-49fc-bc20-6195d209f280)

I think we understand by this point that DVWA is very vulnerable to even simple attacks. Now let's make it more secure by utilizing a WAF. I used modsecurity and here is the guide I followed for the installation: [https://www.linode.com/docs/guides/securing-apache2-with-modsecurity/](installation guide). 

