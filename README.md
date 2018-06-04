# PostgreSQL-Database-with-Metasploit
Config Postgresql with Metasploit
## install and start service
apt install posrgresql
...
systemctl start postgresql.service
...

## change user postgres
root@010618v3:~# su postgres

## Creating a database user
root@010618v3:~# su postgres
postgres@010618v3:/root$ createuser msf_user -P
Enter password for new role:
postgres@010618v3:/root$ createuser msf -P
Enter password for new role:
Enter it again:

## Creating a database
postgres@010618v3:/root$ createdb --owner=msf msf_database
exit
## Connect DB
root@010618v3:~# msfconsole

     ,           ,
    /             \
   ((__---,,,---__))
      (_) O O (_)_________
         \ _ /            |\
          o_o \   M S F   | \
               \   _____  |  *
                |||   WW|||
                |||     |||


       =[ metasploit v4.16.59-dev-                        ]
+ -- --=[ 1769 exploits - 1008 auxiliary - 307 post       ]
+ -- --=[ 537 payloads - 41 encoders - 10 nops            ]
+ -- --=[ Free Metasploit Pro trial: http://r-7.co/trymsp ]

msf > db_connect msf:msf@127.0.0.1:5432/msf_database
[*] Rebuilding the module cache in the background...
msf > db_status
[*] postgresql connected to msf_database
msf >
