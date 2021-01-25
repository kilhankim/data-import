[ec2-user@ip-10-0-1-240 data-import]$ cat load_employees.dump | sed 's/(//' | awk -F ',' '{ print "(" NR "," $2  "," $3 "," $4 "," $5 "," $6 ","  }' | sed 's/;,/,/' > data1.dump
[ec2-user@ip-10-0-1-240 data-import]$ cat data1.dump | sed 's/(//' | awk -F ',' '{ print "(" $1+300025"," $2  "," $3 "," $4 "," $5 "," $6 ","  }' | sed 's/;,/,/' > data2.dump
[ec2-user@ip-10-0-1-240 data-import]$ cat data2.dump | sed 's/(//' | awk -F ',' '{ print "(" $1+300025"," $2  "," $3 "," $4 "," $5 "," $6 ","  }' | sed 's/;,/,/' > data3.dump
[ec2-user@ip-10-0-1-240 data-import]$ cat data3.dump | sed 's/(//' | awk -F ',' '{ print "(" $1+300025"," $2  "," $3 "," $4 "," $5 "," $6 ","  }' | sed 's/;,/,/' > data4.dump



mysql -h milk.c6pxzdq28flg.us-east-1.rds.amazonaws.com -u admin -p < data.sql


