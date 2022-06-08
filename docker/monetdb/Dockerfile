# syntax=docker/dockerfile:1
FROM ghcr.io/oracle/oraclelinux8-instantclient:19 as build
WORKDIR /
RUN yum -y install https://dev.monetdb.org/downloads/epel/MonetDB-release-epel.noarch.rpm
RUN rpm --import https://dev.monetdb.org/downloads/MonetDB-GPG-KEY
#RUN yum -y install MonetDB\*
RUN yum -y install MonetDB-client-odbc
CMD [ "/bin/bash" ]


# Install MonetDB in Oracle Linux container
# yum install https://dev.monetdb.org/downloads/epel/MonetDB-release-epel.noarch.rpm
# Is this ok [y/N]: y
# yum install MonetDB-SQL-server5 MonetDB-client MonetDB-client-odbc
# Is this ok [y/N]: y
# Is this ok [y/N]

# Installing:             
# MonetDB-SQL-server5    
# MonetDB-client         
# MonetDB-client-odbc    
# Installing dependencies:
# MonetDB                
# MonetDB-stream         
# MonetDB5-server        
# libtool-ltdl           
# unixODBC  

# MonetDB-11.43.15-20220520.el8.x86_64                                                                                                          1/8
# MonetDB-SQL-server5-11.43.15-20220520.el8.x86_64                                                                                              2/8
# MonetDB-client-11.43.15-20220520.el8.x86_64                                                                                                   3/8
# MonetDB-client-odbc-11.43.15-20220520.el8.x86_64                                                                                              4/8
# MonetDB-stream-11.43.15-20220520.el8.x86_64                                                                                                   5/8
# MonetDB5-server-11.43.15-20220520.el8.x86_64                                                                                                  6/8
# libtool-ltdl-2.4.6-25.el8.x86_64                                                                                                              7/8
# unixODBC-2.3.7-1.el8.x86_64