---
title: "Сопоставление ограничений key схемы XML (XSD) с ограничениями DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление ограничений key схемы XML (XSD) с ограничениями DataSet
В схеме можно задать ограничение ключа в элементе или атрибуте с помощью элемента **key**.  Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.  
  
 Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.  
  
 В следующей таблице приводятся атрибуты **msdata**, которые указываются в элементе **key**.  
  
|Имя атрибута|Описание|  
|------------------|--------------|  
|**msdata:ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения.  В противном случае имя ограничения указывается атрибутом **name**.|  
|**msdata:PrimaryKey**|Если значение `PrimaryKey="true"` присутствует, свойство ограничения **IsPrimaryKey** имеет значение **true**, делая таким образом это ограничение первичным ключом.  Свойство столбца **AllowDBNull** получает значение **false**, поскольку первичные ключи не могут иметь значение NULL.|  
  
 При преобразовании схемы с заданным ограничением ключа процесс сопоставления создает в таблице ограничение уникальности и присваивает свойству столбца **AllowDBNull** значение **false** в каждом столбце ограничения.  Свойство **IsPrimaryKey** ограничения уникальности также получает значение **false**, если в элементе **key** задано `msdata:PrimaryKey="true"`.  Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.  
  
 В следующем примере схемы элемент **key** задает ограничение ключа в элементе **CustomerID**.  
  
```  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 Элемент **key** указывает, что значения дочернего элемента **CustomerID** элемента **Customers** должны иметь уникальные значения, не равные NULL.  При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Процесс сопоставления схемы XML также создает ограничение **UniqueConstraint** в столбце **CustomerID**, как показано в <xref:System.Data.DataSet>.  \(Для простоты показаны только значимые свойства.\)  
  
```  
  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 В сформированном объекте **DataSet** свойство **IsPrimaryKey** для **UniqueConstraint** имеет значение **true**, поскольку в элементе **key** схема задает `msdata:PrimaryKey="true"`.  
  
 Свойство **ConstraintName** ограничения **UniqueConstraint** в **DataSet** принимает значение атрибута **msdata:ConstraintName**, заданное в элементе схемы **key**.  
  
## См. также  
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)