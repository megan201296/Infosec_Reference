# Password Bruting and Hashcracking

## Table of Contents

* [General](#general)
* [Making Better Passwords](#better)
* [Cracking Passwords/Hashes](#crack)
* [General Cracking Tools](#generalt)
* [App Specific Tools](#appt)
* [Write-ups/Guides](#writeup)
* [Miscellaneous](#misc)
* [Wordlists](#wordlist)
* [Wordlist Generation](#)
* [Talks & Presentations](#)
* [Papers](#papers)



#### Sort


#### End cull





---------------------------
### <a name="general">General</a>
* [How I became a password cracker](https://arstechnica.com/information-technology/2013/03/how-i-became-a-password-cracker/)
* [HashView](https://github.com/hashview/hashview)
	* Hashview is a tool for security professionals to help organize and automate the repetitious tasks related to password cracking. Hashview is a web application that manages hashcat (https://hashcat.net) commands. Hashview strives to bring constiency in your hashcat tasks while delivering analytics with pretty pictures ready for ctrl+c, ctrl+v into your reports.
* [Hashtag](http://www.smeegesec.com/2013/11/hashtag-password-hash-identification.html)
	* Password hash identification tool written in python
* [List of hash types/examples](https://docs.google.com/file/d/0B0TzWBRmg5pWWUtxRTFMbFRRZzA/edit)
* [Password Recovery Speeds](http://www.lockdown.co.uk/?pg=combi)
	* Password cracking time measurements
* [Password cracking, mining, and GPUs](http://blog.erratasec.com/2011/06/password-cracking-mining-and-gpus.html#.VG3xspPF_tw)
* [CredKing](https://github.com/ustayready/CredKing)
	* Password spraying using AWS Lambda for IP rotation




------------------
### <a name="better">Making Better Passwords</a>


[Mnemonic Password Formulas](http://uninformed.org/?v=all&a=33&t=sumry)
*  The current information technology landscape is cluttered with a large number of information systems that each have their own individual authentication schemes. Even with single sign-on and multi-system authentication methods, systems within disparate management domains are likely to be utilized by users of various levels of involvement within the landscape as a whole. Due to this complexity and the abundance of authentication requirements, many users are required to manage numerous credentials across various systems. This has given rise to many different insecurities relating to the selection and management of passwords. This paper details a subset of issues facing users and managers of authentication systems involving passwords, discusses current approaches to mitigating those issues, and finally introduces a new method for password management and recalls termed Mnemonic Password Formulas. 




------------------
### <a name="crack">Cracking Passwords/Hashes</a>
* [Introduction to Cracking Hashes](http://n0where.net/introduction-break-that-hash/)
	* Good introduction source to hash cracking.
* [Cracking Corporate Passwords Exploiting Password Policy Weaknesses - Minga Rick Redm - Derbycon3](https://www.youtube.com/watch?v=qR-qRUbeKAo)
* [HashView](https://github.com/hashview/hashview)
	* Hashview is a tool for security professionals to help organize and automate the repetitious tasks related to password cracking. Hashview is a web application that manages hashcat (https://hashcat.net) commands. Hashview strives to bring constiency in your hashcat tasks while delivering analytics with pretty pictures ready for ctrl+c, ctrl+v into your reports.
* [Cracking Active Directory Passwords or �How to Cook AD Crack"](https://www.sans.org/reading-room/whitepapers/testing/cracking-active-directory-passwords-how-cook-ad-crack-37940)
* [Cracking Corporate Passwords � Exploiting Password Policy Weaknesses - Minga / Rick Redman Derbycon 2013](https://www.irongeek.com/i.php?page=videos/derbycon3/1301-cracking-corporate-passwords-exploiting-password-policy-weaknesses-minga-rick-redman)
* [hcxtools](https://github.com/ZerBea/hcxtools)
	* Small set of tools to capture and convert packets from wlan devices (h = hash, c = capture, convert and calculate candidates, x = different hashtypes) for the use with latest hashcat or John the Ripper. The tools are 100% compatible to hashcat and John the Ripper and recommended by hashcat. This branch is pretty closely synced to hashcat git branch (that means: latest hcxtools matching on latest hashcat beta) and John the Ripper git branch ( "bleeding-jumbo").
* [PACK (Password Analysis and Cracking Toolkit)](https://github.com/iphelix/pack)
	* PACK (Password Analysis and Cracking Toolkit) is a collection of utilities developed to aid in analysis of password lists in order to enhance password cracking through pattern detection of masks, rules, character-sets and other password characteristics. The toolkit generates valid input files for Hashcat family of password crackers.


------------------
### <a name="appt">App Specific Tools(as in single application focus)</a>
* [crackxls2003 0.4](https://github.com/GavinSmith0123/crackxls2003)
	* This program may be used to break the encryption on Microsoft Excel and Microsoft Word file which have been encrypted using the RC4 method, which uses a 40-bit-long key. This was the default encryption method in Word and Excel 97/2000/2002/2003. This program will not work on files encrypted using Word or Excel 2007 or later, or for versions 95 or earlier. It will not work if a file was encrypted with a non-default method. Additionally, documents created with the Windows system locale set to France may use a different encryption method.
* [mod0keecrack](https://github.com/devio/mod0keecrack)
	* mod0keecrack is a simple tool to crack/bruteforce passwords of KeePass 2 databases. It implements a KeePass 2 Database file parser for .kdbx files, as well as decryption routines to verify if a supplied password is correct. mod0keecrack only handles the encrypted file format and is not able to parse the resulting plaintext database. The only purpose of mod0keecrack is the brute-forcing of a KeePass 2 database password.





------------------
#### OCL/Hashcat
* General
	* [OCL hashcat wiki](http://hashcat.net/wiki/)
		* Its the Wiki
	* [OCL hashcat](http://n0where.net/introduction-break-that-hash/)
		* It�s OCL hashcat
* Hashcat attacks
	* [Mask atttack](http://hashcat.net/wiki/doku.php?id=mask_attack)
		* Try all combinations from a given keyspace just like in Brute-Force attack, but more specific. 
	* [Combinator attack](http://hashcat.net/wiki/doku.php?id=combinator_attack)
		* Each word of a dictionary is appended to each word in a dictionary. 
	* [Dictionary attack](http://hashcat.net/wiki/doku.php?id=dictionary_attack)
		* The dictionary attack is a very simple attack mode. It is also known as a �Wordlist attack�. 
	* [Fingerprint Attack](http://hashcat.net/wiki/doku.php?id=fingerprint_attack)
		* The Fingerprint attack is a combination of the results of the expander with a combination engine. It is an automatically generated attack on pattern that works fine on GPGPU. 
	* [Hybrid attack](http://hashcat.net/wiki/doku.php?id=hybrid_attack)
		* Basically, the hybrid attack is just a Combinator attack. One side is simply a dictionary, the other is the result of a Brute-Force attack. In other words, the full Brute-Force keyspace is either appended or prepended to each of the words from the dictionary. That's why it's called �hybrid�. 
	* [Mask attack](http://hashcat.net/wiki/doku.php?id=mask_attack)
		* Try all combinations from a given keyspace just like in Brute-Force attack, but more specific. 
	* [Permutation attack[(http://hashcat.net/wiki/doku.php?id=permutation_attack)
		* Each word in a dictionary generates all permutations of itself. 
	* [Rule Based attack](http://hashcat.net/wiki/doku.php?id=rule_based_attack)
		* The rule-based attack is one of the most complicated of all the attack modes. The reason for this is very simple. The rule-based attack is like a programming language designed for password candidate generation. It has functions to modify, cut or extend words and has conditional operators to skip some, etc. That makes it the most flexible, accurate and efficient attack. 
	* [Table Lookup attack](http://hashcat.net/wiki/doku.php?id=table_lookup_attack)
		* With each word in our dictionary, it automatically generates masks as in a batch of Mask attack. 
	* [Toggle-Case attack](http://hashcat.net/wiki/doku.php?id=toggle_case_attack)
		* For each word in a dictionary, all possible combinations of upper- and lower-case variants are generated. 
	* [OCLHashcat Hash Examples + hash code](https://hashcat.net/wiki/doku.php?id=example_hashes)







### <a name="writeup">Writeups</a>
* [How to crack password hashes efficiently](http://www.dafthack.com/blog/howtocrackpasswordhashesefficiently)
	* Excellent writeup/methodology explanation
* [Building a Better GPU based hash cracking methodology](https://blog.netspi.com/gpu-password-cracking-building-a-bette Penr-methodology/)
	* Bit basic advice but still great advice nonetheless
* [5min Guide to setting up a GPU cracker in the cloud on AWS + a script to automate it all](http://thehackerblog.com/amazon-ec2-gpu-hvm-spot-instance-cracking-setup-tutorial/)
* [Dumping a Domains worth of passwords using mimikatz](http://carnal0wnage.attackresearch.com/2013/10/dumping-domains-worth-of-passwords-with.html)
* [Dump Windows password hashes efficiently - Part 1](http://www.bernardodamele.blogspot.com/2011/12/dump-windows-password-hashes.html)



------------------
### <a name="generalt">Tools</a>
* [Patator](https://github.com/lanjelot/patator)
	* Patator was written out of frustration from using Hydra, Medusa, Ncrack, Metasploit modules and Nmap NSE scripts for password guessing attacks. I opted for a different approach in order to not create yet another brute-forcing tool and avoid repeating the same shortcomings. Patator is a multi-threaded tool written in Python, that strives to be more reliable and flexible than his fellow predecessors.
* [Firefox password cracker](https://github.com/pradeep1288/ffpasscracker)
* [Cracklord](https://github.com/jmmcatee/cracklord)
	* CrackLord is a system designed to provide a scalable, pluggable, and distributed system for both password cracking as well as any other jobs needing lots of computing resources. Better said, CrackLord is a way to load balance the resources, such as CPU, GPU, Network, etc. from multiple hardware systems into a single queueing service across two primary services: the Resource and Queue. It won't make these tasks faster, but it will make it easier to manage them.
* [Dagon](https://github.com/Ekultek/Dagon)
	* Named after the prince of Hell, Dagon (day-gone) is an advanced hash cracking and manipulation system, capable of bruteforcing multiple hash types, creating bruteforce dictionaries, automatic hashing algorithm verification, random salt generation from Unicode to ASCII, and much more.
* [Gladius](https://github.com/praetorian-inc/gladius)
	* Automated Responder/secretsdump.py cracking. Gladius provides an automated method for cracking credentials from various sources during an engagement. We currently crack hashes from Responder, secretsdump.py, and smart_hashdump.



------------------
### <a name="wordlistgen">Wordlist Generation</a>
* [GitDigger](https://github.com/wick2o/gitdigger)
	* gitDigger: Creating realworld wordlists from github hosted data.
* [Wikigen](https://github.com/zombiesam/wikigen)
	* A script to generate wordlists out of wikipedia pages. Should support most of the subdomains. Some ugly code may occur
* [CeWL](http://digi.ninja/projects/cewl.php)
	* CeWL is a ruby app which spiders a given url to a specified depth, optionally following external links, and returns a list of words which can then be used for password crackers such as John the Ripper.
* [Generating Wordlists](http://netsec.ws/?p=457)
* [Creating Wordlists with Crunch](http://adaywithtape.blogspot.com/2011/05/creating-wordlists-with-crunch-v30.html)
* [OMEN: Ordered Markov ENumerator](https://github.com/RUB-SysSec/OMEN)
	* OMEN is a Markov model-based password guesser written in C. It generates password candidates according to their occurrence probabilities, i.e., it outputs most likely passwords first. OMEN significantly improves guessing speed over existing proposals. If you are interested in the details on how OMEN improves on existing Markov model-based password guessing approaches, please refer to OMEN: Faster Password Guessing Using an Ordered Markov Enumerator.
* [cupp.py - Common User Passwords Profiler](https://github.com/Mebus/cupp)
	* The most common form of authentication is the combination of a username and a password or passphrase. If both match values stored within a locally stored table, the user is authenticated for a connection. Password strength is a measure of the difficulty involved in guessing or breaking the password through cryptographic techniques or library-based automated testing of alternate values. A weak password might be very short or only use alphanumberic characters, making decryption simple. A weak password can also be one that is easily guessed by someone profiling the user, such as a birthday, nickname, address, name of a pet or relative, or a common word such as God, love, money or password. That is why CUPP has born, and it can be used in situations like legal penetration tests or forensic crime investigations.
* [Mentalist](https://github.com/sc0tfree/mentalist)
	* Mentalist is a graphical tool for custom wordlist generation. It utilizes common human paradigms for constructing passwords and can output the full wordlist as well as rules compatible with Hashcat and John the Ripper.
	* [Wiki](https://github.com/sc0tfree/mentalist/wiki)




------------------
### <a name="wordlists">Wordlists</a>
* [Crackstation�s Password Cracking Dictionary 1.5b words](https://crackstation.net/buy-crackstation-wordlist-password-cracking-dictionary.htm)
	* HIGHLY recommended
* [WPA/WPA2 Dictionaries](https://wifi0wn.wordpress.com/wepwpawpa2-cracking-dictionary/)
* [SkullSecurity Password lists](https://wiki.skullsecurity.org/Passwords)
* [Crack Me if You Can - Defcon 2010](http://contest-2010.korelogic.com/wordlists.html)
* [Probable-Wordlists](https://github.com/berzerk0/Probable-Wordlists)
	* Wordlists sorted by probability originally created for password generation and testing
* [BEWGor](https://github.com/berzerk0/BEWGor)
	* Bull's Eye Wordlist Generator
* [SecLists](https://github.com/danielmiessler/SecLists)
* [statistically-likely-usernames](https://github.com/insidetrust/statistically-likely-usernames)
	* This resource contains wordlists for creating statistically likely usernames for use in username-enumeration, simulated password-attacks and other security testing tasks.
* [Oracle Default Password List](http://www.petefinnigan.com/default/default_password_list.htm)
* [Passhunt](https://github.com/Viralmaniar/Passhunt/blob/master/README.md)
	* Passhunt is a simple tool for searching of default credentials for network devices, web applications and more. Search through 523 vendors and their 2084 default passwords.

	
------------------
### Talks & Presentations
* [Cracking Corporate Passwords Exploiting Password Policy Weaknesses - Minga Rick Redm - Derbycon3](https://www.youtube.com/watch?v=qR-qRUbeKAo)



------------------
### <a name="papers">Papers</a>

* [Optimizing computation of Hash Algorithms as an attacker](https://hashcat.net/events/p13/js-ocohaaaa.pdf)
* [Attacking NTLM with Precomputed Hashtables](http://uninformed.org/?v=all&a=13&t=sumry)
	* Breaking encrypted passwords has been of interest to hackers for a long time, and protecting them has always been one of the biggest security problems operating systems have faced, with Microsoft's Windows being no exception. Due to errors in the design of the password encryption scheme, especially in the LanMan(LM) scheme, Windows has a bad track in this field of information security. Especially in the last couple of years, where the outdated DES encryption algorithm that LanMan is based on faced more and more processing power in the average household, combined with ever increasing harddisk size, made it crystal clear that LanMan nowadays is not just outdated, but even antiquated. 
* [Website Dedicated to Password Research](http://www.passwordresearch.com/papers/pubindex.html)
	* A core objective of the Password Research Institute is to improve the industry awareness of existing authentication research. Many valuable solutions for the problems associated with authentication have gone unnoticed by the people interested in, or responsible for, authentication security. This project will compile and share a comprehensive, but moderated, index of password and authentication related research papers. We aim to share the details of useful papers, provide access to the papers, and encourage collaboration between authors and other security professionals.
* [When Privacy meets Security: Leveraging personal information for password cracking - M. D�rmuth,A. ChaabaneD. Perito,C. Castelluccia]()
	* Passwords are widely used for user authentication and, de- spite their weaknesses, will likely remain in use in the fore seeable future. Human-generated passwords typically have a rich structure , which makes them susceptible to guessing attacks. In this paper, we stud y the effectiveness of guessing attacks based on Markov models. Our contrib utions are two-fold. First, we propose a novel password cracker based o n Markov models, which builds upon and extends ideas used by Narayana n and Shmatikov (CCS 2005). In extensive experiments we show that it can crack up to 69% of passwords at 10 billion guesses, more than a ll probabilistic password crackers we compared against. Second, we systematically analyze the idea that additional personal informatio n about a user helps in speeding up password guessing. We find that, on avera ge and by carefully choosing parameters, we can guess up to 5% more pas swords, especially when the number of attempts is low. Furthermore, we show that the gain can go up to 30% for passwords that are actually b ased on personal attributes. These passwords are clearly weaker an d should be avoided. Our cracker could be used by an organization to detect and reject them. To the best of our knowledge, we are the first to syst ematically study the relationship between chosen passwords and users� personal in- formation. We test and validate our results over a wide colle ction of leaked password databases.
* [PassGAN](https://github.com/brannondorsey/PassGAN)
	* This repository contains code for the [PassGAN: A Deep Learning Approach for Password Guessing paper](https://arxiv.org/abs/1709.00440). The model from PassGAN is taken from [Improved Training of Wasserstein GANs](https://arxiv.org/abs/1704.00028) and it is assumed that the authors of PassGAN used the [improved_wgan_training tensorflow](https://github.com/igul222/improved_wgan_training) implementation in their work. For this reason, I have modified that reference implementation in this repository to make it easy to train (train.py) and sample (sample.py) from. 








