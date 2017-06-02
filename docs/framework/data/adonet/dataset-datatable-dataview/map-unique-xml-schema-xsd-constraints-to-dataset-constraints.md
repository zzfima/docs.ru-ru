---
title: "Сопоставление ограничений уникальности схемы XML (XSD) с ограничениями DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление ограничений уникальности схемы XML (XSD) с ограничениями DataSet
В схеме на языке XSD элемент **unique** накладывает на элемент или атрибут ограничение уникальности.  В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML\-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.  
  
 В следующей таблице приведено описание атрибутов **msdata**, которые можно задать в элементе **unique**.  
  
|Имя атрибута|Описание|  
|------------------|--------------|  
|**msdata:ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения.  В противном случае имя ограничения указывается атрибутом **name**.|  
|**msdata:PrimaryKey**|Если в элементе **unique** присутствует `PrimaryKey="true"`, то создается ограничение уникальности со свойством **IsPrimaryKey**, которому задано значение **true**.|  
  
 В следующем примере показана схема XML, в которой элемент **unique** используется для наложения ограничения уникальности.  
  
```  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique      
msdata:ConstraintName="UCustID"      
name="UniqueCustIDConstr" >        
<xs:selector xpath=".//Customers" />        
<xs:field xpath="CustomerID" />      
</xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 Элемент **unique** в этой схеме указывает, что для всех элементов **Customers** в экземпляре документа значение дочернего элемента **CustomerID** должно быть уникальным.  При построении объекта **DataSet** процесс сопоставления считывает эту схему и формирует следующую таблицу:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Процесс сопоставления также налагает ограничение уникальности на столбец **CustomerID**, как показано в следующем объекте **DataSet**.  \(Для простоты показаны только значимые свойства.\)  
  
```  
  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID  
      Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 В сформированном объекте **DataSet** для ограничения уникальности свойство **IsPrimaryKey** имеет значение **False**.  Свойство **unique** для столбца указывает, что значения в столбце **CustomerID** должны быть уникальными \(однако они могут быть null, как указано свойством **AllowDBNull** столбца\).  
  
 В случае изменения схемы и задания необязательному атрибуту **msdata:PrimaryKey** значения **True**, создается ограничение уникальности для таблицы.  Свойство столбца **AllowDBNull** имеет значение **False**, а свойство **IsPrimaryKey** набора ограничений \- значение **True**, в результате чего столбец **CustomerID** становится столбцом первичного ключа.  
  
 Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML.  В следующем примере демонстрируется, как указать, что сочетание значений **CustomerID** и **CompanyName** должно быть уникальным для всех **Customers** в любом экземпляре путем добавления в схему еще одного элемента **xs:field**.  
  
```  
  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Вот это ограничение, которое создано в итоговом объекте **DataSet**.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## См. также  
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)