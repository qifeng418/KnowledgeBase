## JDBC


## MyBatis

### Q: Understanding of MyBatis

(Baidu Encyclopedia) MyBatis is an excellent persistence layer framework that supports custom SQL, stored procedures, and advanced mapping. MyBatis avoids almost all JDBC code and manually sets parameters and gets result sets. MyBatis can use simple XML or annotations to configure and map native information, mapping interfaces and Java POJOs (Plain Ordinary Java Objects) to records in the database.

Mybatis separates the sql statement from the Java source program and writes it in a separate XML file, which brings great convenience to the maintenance of the program. Ibatis encapsulates the invocation details of the underlying JDBC API and automatically converts the result set into a Java Bean object, greatly simplifying the repetitive work of Java database programming. Because Ibatis requires programmers to write sql statements themselves, programmers can flexibly control sql statements in combination with the characteristics of the database itself, so it can achieve higher query efficiency than hibernate and other automatic orm frameworks, and can complete complex queries.

