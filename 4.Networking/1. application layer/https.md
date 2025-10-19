to use https you need a ssl certificate which u receive by sending a csr file to a provider 
your web server installs this csr file and then browser trusts it

public key - in the certificate
private key - on the server 

browser encripts data with the public key
it can only be decripted with the private key

CA = Certificate Authority (lets encript, DigiCert)


openssl -> 




so who is this provider? how long does this cerificate last, what si the criteria of others accepting my reuwest. what is this key u keep talking ab. so basically instead of http which doesnt encrupt data not https ecripts everythign that is sent. and how does it encript it? and who encripts ir? why? do i need to pay? why arent all wbsites https then?