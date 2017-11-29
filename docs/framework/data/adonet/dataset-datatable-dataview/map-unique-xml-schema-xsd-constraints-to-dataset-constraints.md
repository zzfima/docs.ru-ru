---
title: "Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66183768b5b48608dc69a4021b27816595c43b4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
В схему языка определения схемы XML **уникальный** элемент указывает на элемент или атрибут ограничение уникальности. В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.  
  
 В следующей таблице описываются **msdata** атрибутов, которые можно указать в **уникальный** элемента.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае **имя** атрибут содержит значение имени ограничения.|  
|**msdata: PrimaryKey**|Если `PrimaryKey="true"` присутствует в **уникальный** , ограничения unique создается элемент с **IsPrimaryKey** свойство **true**.|  
  
 В следующем примере показано схему XML, который использует **уникальный** элемента, чтобы указать ограничение уникальности.  
  
```xml  
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
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 **Уникальный** элемента в схеме указывает, что для всех **клиентов** элементы в документе экземпляра значение **CustomerID** дочерний элемент должен быть уникальным. В здании **набора данных**, процесс сопоставления считывает эту схему и формирует следующую таблицу:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Процесс сопоставления также налагает ограничение уникальности на **CustomerID** столбца, как показано в следующем примере **набора данных**. (Для простоты показаны только значимые свойства.)  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 В **DataSet** сформированном **IsPrimaryKey** свойству **False** для ограничения уникальности. **Уникальный** для столбца указывает, что **CustomerID** значения столбца должны быть уникальными (Однако они могут быть пустая ссылка, в соответствии с **AllowDBNull** свойство столбца).  
  
 Если изменения схемы и задания необязательному **msdata: PrimaryKey** значение для атрибута **True**, создается ограничение уникальности на таблицу. **AllowDBNull** столбца задано значение **False**и **IsPrimaryKey** свойство ограничений-значение **True**, в результате чего **CustomerID** столбец столбцом первичного ключа.  
  
 Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML. В следующем примере показано, как указать, что сочетание **CustomerID** и **CompanyName** значения должны быть уникальными для всех **клиентов** в любом экземпляре путем Добавление другого **xs: field** элемента в схеме.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Это ограничение, которое создается в результате **набора данных**.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>См. также  
 [Сопоставление ограничений XML схемы (XSD) для ограничения набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Создание отношений наборов данных из XML-схемы (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
