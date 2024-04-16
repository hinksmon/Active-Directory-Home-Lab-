# Active-Directory-Home-Lab-

## Objective
This Active Directory project is aimed to start from 0 to a fully functional domain enviornment built on prem. Then to test it by brute forcing the domain and viewing the logs created by the attack. Well start by building a logical diagram, then we will install vm's for Kali Linux, Windows Server, Windows 10, and Splunk. Then well configure and install sysmon and splunk to query for telemetry and make your own alerts dashboards, and alerts. Then well configure active directory on our windows server and how to promote it to our domain controller while also creating new domain users that can log in to the new domain. Finally we will be using Kali Linux to generate a brute force attack targeting one of the users we created, we will also download atomic red team (ART) to show you what kind of telemetry that can generate too.



### Skills Learned

- Add users using Active Directory
- Install and implement Splunk into a target machiene
- How to set up an Active Directory onto a VM
### Tools Used

- Active Directory 
- Splunk
- Virtual Box
- ART
- Kali Linux

## Steps
1. Firstly we are going to setup a logical diagram to plan how we want to build out our lab, as well as give our different tools there own IPs

![Screenshot (2)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/9e272d74-1734-4ab0-b9dc-2cb5b435fc4d)

2. Then we are going to download and configure our vitual machienes on virtual box

![Screenshot (19)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/57ab346c-4682-4d60-a07b-da40d56d06d6)

3. Then once everything is installed I then installed and configured splunk and sysmon onto the windows target machiene

![Screenshot (22)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/932a9b98-c349-4008-a880-5879bc56200c)

![Screenshot (26)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/52ce8c20-4687-4dd7-abf7-2bf3ad9d85ae)


4. After they were installed I changed the target machienes name and ip configs to match the ones from our diagram and also download splunk universal forwarder 

![Screenshot (32)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/0effd2f9-19ed-4a41-ab4a-27cff9ad761b)


![Screenshot (33)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/977148b1-2988-457b-89b1-7273d0643b03)

 ![Screenshot (35)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/8a1cbddb-35c2-49ec-873d-7ff512e69a6c)

 5. After that I downloaded sysmon to use for my logs. I used the specific logs by Olaf for my configuration

![Screenshot (38)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/c5d27fa6-925d-422b-8d85-a35a94374d89)

![Screenshot (40)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/48a5c658-0209-46f8-88a3-7c05635220d1)

6. Next I connected my logs from splunk to my windows controller and also change the ipconfig to a static ip from my diagram


![Screenshot (47)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/b7dfff32-f178-481f-9fa1-6346bb6d7ff4)

![Screenshot (48)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/df861ef1-4116-4412-baca-df4cec0d0cf5)


7. After that I added ADDS (Active Directory Domain Services) to my Windows VM and added a new users and groups 

![Screenshot (49)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/8f41a9d4-1d6c-45d9-9ff3-c989a1384c50)

![Screenshot (50)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/6ec3025f-d766-404b-9f34-f8e70c30e94f)

![Screenshot (51)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/6bd69051-453c-4efc-9bd2-f4e85835ed95)

8. Then I switched to my windows target machiene and joined it to the newly created domain and authenticated using jenny smith's account.

![Screenshot (52)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/aa45c75b-c2e1-45c1-954b-1aedae5e23a8)

![Screenshot (53)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/3c726c73-ad6e-4459-a103-d48ff6048fe6)

9. Next I set up a static ip to the kali linux machine as per my diagram then updated the repository on the system and installed crowbar so we can brute force passwords

![Screenshot (68)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/966a26b8-53fe-4efc-9fc1-669f0d9b4f56)

![Screenshot (67)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/00d701a4-54e5-4a4f-af05-92e400fd6c24)

![Screenshot (69)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/e46beb35-2d5a-4f17-ac68-8e4b210b5249)


10. After that I enabled RDP and use crowbar to brute force the passwords for the users we created and finding the sysmon log of it in splunk 

![Screenshot (70)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/c0c181b6-076c-45a7-8fc2-563bdefbdbb2)

![Screenshot (71)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/8a7991a5-2f52-4259-85db-326a9e454cd9)

![Screenshot (63)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/97b9e0ce-0ea1-49cf-a630-2d19bb338866)


11. Finally I installed ART (Atomic Red Team) on my target machiene and run some tests on it 

![Screenshot (64)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/83eb398a-d402-4dc1-83c1-6738821a9342)

![Screenshot (66)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/d398fd72-932b-45fb-89ac-5f5326d98510)

![Screenshot (73)](https://github.com/hinksmon/Active-Directory-Home-Lab-/assets/162920003/34164daa-3fae-494f-b458-6e87585d5c2f)



