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

I think we understand by this point that DVWA is very vulnerable to even simple attacks. Now let's make it more secure by utilizing a WAF. I used modsecurity and here is the guide I followed for the installation: [https://www.linode.com/docs/guides/securing-apache2-with-modsecurity/]. After installing the WAF in important thing is to activate it in /etc/modsecurity/modsecurity.conf by turning SecRuleEngine to On like the following screenshot:

![sec rules on](https://github.com/user-attachments/assets/9b8ebb77-1e99-42a1-8bca-9a230d2c4f30)

After turning it on if we try our attacks again none of them will work:

![xss blocked 1](https://github.com/user-attachments/assets/5256e6bf-284c-4edd-8876-e297e03d2d7c)
![xss blocked 2](https://github.com/user-attachments/assets/705fb139-74b1-45ca-8477-8f7a76d2d730)
![sql blocked](https://github.com/user-attachments/assets/56f96685-1be1-47f3-b0a5-931baae64c9c)
![xss blocked 2](https://github.com/user-attachments/assets/705fb139-74b1-45ca-8477-8f7a76d2d730)
![comm](https://github.com/user-attachments/assets/8bbc4aeb-0230-4a78-b8f5-e474a2689818)
![xss blocked 2](https://github.com/user-attachments/assets/705fb139-74b1-45ca-8477-8f7a76d2d730)
![path](https://github.com/user-attachments/assets/4ab33878-3b1b-4bf3-b4eb-a1174116e553)
![php up](https://github.com/user-attachments/assets/16f8bbcd-8845-4b46-a25e-57a1412c8321)
![xss blocked 2](https://github.com/user-attachments/assets/705fb139-74b1-45ca-8477-8f7a76d2d730)




