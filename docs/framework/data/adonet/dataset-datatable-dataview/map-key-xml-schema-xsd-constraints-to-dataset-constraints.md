---
title: "Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f5247d0ccfd2ceec641ff29d29b889a55c1a5e12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме, можно задать ограничение ключа в элементе или атрибуте с помощью **ключ** элемента. Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.  
  
 Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.  
  
 В следующей таблице описываются **msdata** атрибутов, которые можно указать в **ключ** элемента.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае **имя** атрибут содержит значение имени ограничения.|  
|**msdata: PrimaryKey**|Если `PrimaryKey="true"` присутствует, **IsPrimaryKey** ограничение свойству **true**, делая его первичного ключа. **AllowDBNull** столбца задано значение **false**, поскольку первичные ключи не могут иметь значения null.|  
  
 При преобразовании схемы, в котором указывается ограничение ключа, процесс сопоставления создает ограничение уникальности на таблицу с **AllowDBNull** свойство столбца значение **false** для каждого столбца в ограничение. **IsPrimaryKey** уникальности задается **false** пока не задана `msdata:PrimaryKey="true"` на **ключ** элемента. Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.  
  
 В следующем примере схемы **ключ** элемент задает ограничение ключа на **CustomerID** элемента.  
  
```xml  
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
  
 **Ключ** элемент указывает, что значения **CustomerID** дочерний элемент элемента **клиентов** элемент должен содержать уникальные значения и не может иметь значение null. При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Процесс сопоставления схемы XML также создает **UniqueConstraint** на **CustomerID** столбца, как показано в следующем примере <xref:System.Data.DataSet>. (Для простоты показаны только значимые свойства.)  
  
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
  
 В **набора данных** , создается **IsPrimaryKey** свойство **UniqueConstraint** равно **true** так как схемы Указывает `msdata:PrimaryKey="true"` в **ключ** элемента.  
  
 Значение **ConstraintName** свойство **UniqueConstraint** в **DataSet** значение **msdata: ConstraintName** атрибут, указанный в **ключ** элемента в схеме.  
  
## <a name="see-also"></a>См. также  
 [Сопоставление ограничений XML схемы (XSD) для ограничения набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Создание отношений наборов данных из XML-схемы (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
