Open Source Intelligence
	Shows what is available resources is public for you.


What information can you get from a company without doing anything  directly to them? 
	Linked in profiles, shows you who is a high target inside of the company
	Wireshark (passive recon)
	Names of employees
	where the employees work
	What their interests are (hobbies) 
		Example: 
		Chess is a hobby --> Do a spear fishing email
	Where a webserver is located
		Crutial network severs are located? ex: 137.45.192.100
		Looking for other servers or systems on 137.45.192.100 same network address
	Where email services are located 
	What email clients are they using? 
		(gmail, hotmail, outlook?)


We get a response from dig
	We look at the v=spf1 because it shows what email services provider it uses, and what cloud provider it is on. We then look at the next line or at the end of the line
	Sender policy framework
		"~all" means that you can forward to any provider of email that you want. Since we use outlook at school, we allow it to be sent to gmail. 
		"-A"