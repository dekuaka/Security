# OWASP TOP 10(2017)
## Injections
SQL Injection
### Defense
* query parameterization: prepared statement
* valid user input
* limit the data send back (limit the exposure)
## Broken authentication
allow the users to get into the web application without proper credentials

session id is created, when the user tries to access to the web application

* credential stuffing: try the stolen user/passwd over and over again
* automated attacks: random usernames and random passwd
* default username and passwd  
ex. tab is closed, browser isn't. session id is stored.
### Defense
* muti factor auth: token on cellphone
* passwd checking: proactive method. check the db to make sure the popular passwd isn't in the db
* passwd complexity: complexity requirement
* limit failed login
* server side session management: new random session id, the initial session id is not usable
## Sensitive data exposure
![image](https://user-images.githubusercontent.com/57356839/111084890-1043ec80-84eb-11eb-9d07-c30826afd2c4.png)
### Defense
* classify data
* apply control
* encrypt data at rest
* strong ciphers
* possible PFS and/or HSTS
## XML External entities(XXE)
parse some bad data
![image](https://user-images.githubusercontent.com/57356839/111085220-c3611580-84ec-11eb-99bd-9f477e345d5a.png)

attackers put some malicious payload to external entity  
ex: 
* run system command  
* java xml has vulnerability
* billion laughs  
'''
<xml version 1.0>
<DOCTYPE lolz
<ENTITY lol1 lol1;lol1
...
...
...     lol9
<lolz> &lol9 <lolz>
'''
  
### Defense
* disable DTD process
* disable xml
* input validation
* Source code analysis
* Dynamic application security testing or DAST
* firewall

## Broken access control
![image](https://user-images.githubusercontent.com/57356839/111238048-a996ff80-85cc-11eb-835f-22b1df9d6fb7.png)

normal users access to the admin function

DAST TOOL/SAAS(static security testing) source code analyzing tool  
manual testing  
ex: webapp.com/admin_info  
webapp.com/acctinfo?acct=1234 get into the user account. it is broken access control
### Defense
* trusted server side code
* DAST/SAAS
* deny by default
* implement the access control and reuse them
* log your failure
* rate limit access/defense the automated tool
* least priviledge


## Security misconfiguration

## Cross site script(XSS)
## Insecure deserialization
## Using components with known vulnerabilities
## Insufficient logging and monitoring
