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
		(Gmail, Hotmail, outlook?)


We get a response from dig
	We look at the v=spf1 because it shows what email services provider it uses, and what cloud provider it is on. We then look at the next line or at the end of the line
	Sender policy framework
		"~all" means that you can forward to any provider of email that you want. Since we use outlook at school, we allow it to be sent to email. 
		"-all" means outlook only, tilde means it will accept any email service provider.
			The providers are where the emails will originate from. In this one, it will originate from boardbooks.com, outlook.com, or elluciancloud.com. ![[{76BA3B2B-62AA-44EC-ADFA-D0A0122F3085}.png]]
			
			This does not mean that it does not ALWAYS end up in 