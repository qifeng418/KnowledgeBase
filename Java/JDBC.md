## JDBC


## MyBatis

### Q: Understanding of MyBatis
[Answer Reference](https://www.programmersought.com/article/8568335616/)

mybatis is an excellent java-based persistence layer framework, which encapsulates jdbc internally, so that developers only need to pay attention to the sql statement itself, without the effort to deal with the complicated process of loading drivers, creating connections, creating statements, etc. .

mybatis configures various statements to be executed by xml or annotation, and maps the dynamic parameters of sql in the java object and statement to generate the final executed SQL statement. Finally, the mybatis framework executes sql and maps the result to Java object and return.

MyBatis supports custom SQL, stored procedures, and advanced mapping. MyBatis avoids almost all JDBC code and manually sets parameters and gets result sets. MyBatis can use simple XML or annotations to configure and map native information, mapping interfaces and Java POJOs to records in the database.


### Q: Mybatis programming steps?
1. create SqlSessionFactoryBuilder

2. create sqlSessionFactory by SqlsesionFactoryBuilder   

3. create sqlSession by SqlSessionFactory     

4. by performing a database operation sqlSession   

5. calls session.commit() to commit the transaction   

6. calls session.close() to close the session

### Q: The advantages of Mybait?

(1) Easy to learn, easy to use (compared to Hibernate) --- Based on SQL programming;

(2) Compared with JDBC, it reduces the code amount by more than 50%, eliminates the JDBC massive redundant code, and does not require manual switch connection;

(3) Very compatible with various databases (because MyBatis uses JDBC to connect to the database, so as long as the JDBC-supported database MyBatis supports it, and JDBC provides extensibility, so as long as the database has a jar for Java, you can It is compatible with MyBatis), developers do not need to consider the differences in the database.

(4) Good integration with Spring;

(5) MyBatis is quite flexible and does not impose any influence on the existing design of the application or database. SQL is written in XML, completely separated from the program code, and the coupling between sql and program code is removed, which facilitates unified management and optimization. Reusable.

(6) Provide mapping labels to support ORM field relationship mapping between objects and databases.

(7) A number of third-party plugins (paged plugins / reverse engineering) are provided;


### Q: The shortcomings of the MyBatis framework?

(1) The writing of SQL statements is relatively large, especially when there are many fields and related tables, and this is especially true. There are certain requirements for developers to write SQL statements.

(2) The SQL statement depends on the database, resulting in poor portability of the database, and the database cannot be changed at will.


### Q: Occasions MyBatis framework is used?

(1) MyBatis focuses on SQL itself and is a flexible enough DAO layer solution.

(2) MyBatis will be a good choice for projects with high performance requirements or more demand changes, such as Internet projects.

### Q: What is the difference between MyBatis and Hibernate?

Mybatis is different from hibernate. It is not an ORM framework. Because MyBatis requires programmers to write Sql statements themselves, but mybatis can flexibly configure the SQL statements to be run through XML or annotation, and map java objects and sql statements. Generate the final execution of sql, and finally map the results of the sql execution to generate a java object.

Mybatis has a low learning threshold and is easy to learn. The programmer directly writes the original sql, which can strictly control the execution performance of sql and has high flexibility. It is very suitable for software development with low requirements on relational data models, such as Internet software and enterprise operations. Software, etc., because such software needs change frequently, but the demand changes require rapid output. However, the premise of flexibility is that mybatis cannot achieve database independence. If you need to implement software that supports multiple databases, you need to customize multiple sets of sql mapping files, which is a lot of work.

Hibernate object / relationship mapping ability, database independence, for the relationship model high software (such as fixed-demand custom software) if you use hibernate development can save a lot of code and improve efficiency. But Hibernate's shortcomings are high learning thresholds, higher proficiency thresholds, and how to design O/R mappings. How to balance the performance and object models, and how to use Hibernate requires a lot of experience and ability.

### Q: What is the difference between #{} and ${}?

#{} is precompiled, ${} is a string replacement.

When Mybatis processes #{}, it replaces #{} in sql with a ?, and calls the set method of PreparedStatement to assign a value;

When Mybatis processes ${}, it replaces ${} with the value of the variable.

Using #{} can effectively prevent SQL injection and improve system security.

### Q: What should I do if the attribute name in the entity class is different from the field name in the table?

Type 1: By defining the alias of the field name in the sql statement of the query, the alias of the field name is the same as the attribute name of the entity class.
```xml
    <select id=”selectorder” parametertype=”int” resultetype=”me.gacl.domain.order”>
       select order_id id, order_no orderno ,order_price price form orders where order_id=#{id};
    </select>
```

Type 2: Map the one-to-one correspondence between field names and entity class attribute names by <resultMap>
```xml
 <select id="getOrder" parameterType="int" resultMap="orderresultmap">
        select * from orders where order_id=#{id}
    </select>
 
   <resultMap type=”me.gacl.domain.order” id=”orderresultmap”>
        <!–Map the primary key field with the id attribute –>
        <id property=”id” column=”order_id”>
        <!–Use the result attribute to map non-primary key fields, property to entity class attribute names, and column to attributes in the data table –>
        <result property = “orderno” column =”order_no”/>
        <result property=”price” column=”order_price” />
    </reslutMap>
```

### Q: 

### Q: 

### Q: 

### Q: 
