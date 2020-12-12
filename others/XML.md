[TOC]

## 📖 XML

[XML Tutorial Reference](https://www.w3schools.com/xml/default.asp)
### Q: What is a markup language?
Markup languages are designed for presentation of text in different formats, and it can also be used for transporting and storing data. This markup language specifies the code for formatting, layout and style of data .This markup code is called Tag.

HTML and XML are examples of Markup Language.

### Q: What is XML?
XML is called Extensible Markup Language which is designed to carry, transport and store data. XML tags are not as predefined as HTML, but we can define our own user tags for simplicity. It mainly concentrates on storing of data, not on displaying of data.

### Q: What are the features of XML?
• Very easy to learn and implement

• XML files are text files, and no editor is required

• Minimal and a limited number of syntax rules in XML

• It is extensible, and it specifies that structural rules of tags

### Q: What are the differences between HTML and XML?
| HTML | XML |
| --- | --- |
| Markup language used to display data | Markup language used to store data |
| Case Insensitive | Case sensitive |
| Designing web page | Used to transport and store data |
| Predefined Tags | Custom Tags |
| Does not Preserve white spaces | Preserve white spaces |
| Static | Dynamic |


### Q: Which tag is used to find the version of XML and the syntax?
Declaring the XML version is very important for each XML document and platform needs to be specified in which it is running.
```XML
<?xml version=”1.1” encoding=”|ISO-8859-1|”?>
```

### Q: What are the basic rules while writing XML?
• All XML should have a root element

• All tags should be closed

• XML tags are case sensitive

• All tags should be nested properly

• Tag names cannot contain spaces

• Attribute value should appear within quotes

• White space is preserved

### Q: What is XML DOM (XML Document)?
Just like HTML, the XML DOM defines a standard way for accessing and manipulating XML documents. It presents an XML document as a tree-structure.

### Q: DOM Vs SAX
|| DOM(Document Object Model) Parser | SAX (Simple API for XML) Parser |
| --- | --- | --- |
| Abbreviation | DOM stands for Document Object Model | SAX stands for Simple API for XML Parsing |
| Type |Load entire memory and keep in tree structure | event based parser |
| Size of Document | good for smaller size	| good to choose for larger size of file |
| Load | Load entire document in memory | does not load entire document |
| Suiable | better suitable for smaller and efficient memory | SAX is suitable for larger XML doc |

### Q: What is XPath (XML Path)?
XPath is used to find information in an XML document and contains standard functions. XPath is the major element in XSLT, and it is w3c recommendation.

### Q: What is an attribute?
An attribute provides more or additional information about an element than otherwise.

### Q: What is XML Element?
An XML document contains XML Elements, and it starts from an element’s start tag to end tag. It can contain:

• Other elements within main element

• An Attribute

• text

### Q: What is CDATA?
CDATA is unparsed character data that cannot be parsed by the XML parser. Character < and > are illegal in XML elements. CDATA section starts with <![CDATA[“ and end with “]]>”.

### Q: What are XML Namespaces?
XML namespaces are used to avoid element name conflicts, and it can be avoided by using prefix before the name.

### Q: What is XML Parser?
XML Parser is used to convert from XML document into an XML DOM object which can be written in Javascript.

### Q: What is XSL (eXtensible Stylesheet Language)?
XSL is a language used with XML for expressing style sheets as like CSS. It describes how to display an XML document for a given type.

### Q: What is a DTD (Document Type Definition) ?
A DTD defines the structure and the legal elements and attributes of an XML document. With a DTD, independent groups of people can agree on a standard DTD for interchanging data. An application can use a DTD to verify that XML data is valid.

### Q: What is an XML Schema?
An XML Schema describes the structure of an XML document. The XML Schema language is also referred to as XML Schema Definition (XSD).

The purpose of an XML Schema is to define the legal building blocks of an XML document.

• The elements and attributes that can appear in a document

• The number of (and order of) child elements

• Data types for elements and attributes

• Default and fixed values for elements and attributes

### Q: 


