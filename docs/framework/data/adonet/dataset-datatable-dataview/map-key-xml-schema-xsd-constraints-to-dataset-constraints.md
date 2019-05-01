---
title: Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034233"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме, можно задать ограничение ключа в элементе или атрибуте с помощью **ключ** элемент. Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.  
  
 Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.  
  
 В следующей таблице описываются **msdata** атрибуты, которые можно указать в **ключ** элемент.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае **имя** атрибут содержит значение имени ограничения.|  
|**msdata: PrimaryKey**|Если `PrimaryKey="true"` присутствует, **IsPrimaryKey** ограничение свойству **true**, делая его первичный ключ. **AllowDBNull** столбца задано значение **false**, поскольку первичные ключи не могут иметь значения null.|  
  
 При преобразовании схемы, в котором указывается ограничение ключа, процесс сопоставления создает ограничение уникальности для таблицы с **AllowDBNull** свойство столбца, значение **false** для каждого столбца в ограничение. **IsPrimaryKey** ограничения уникальности также задано значение **false** пока не задана `msdata:PrimaryKey="true"` на **ключ** элемент. Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.  
  
 В следующем примере схемы **ключ** элемент задает ограничение ключа на **CustomerID** элемент.  
  
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
  
 **Ключ** элемент указывает, что значения **CustomerID** дочерний элемент элемента **клиентов** элемент должен содержать уникальные значения и не может иметь значения null. При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Сопоставление схем XML также создает **UniqueConstraint** на **CustomerID** столбца, как показано в следующем примере <xref:System.Data.DataSet>. (Для простоты показаны только значимые свойства.)  
  
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
  
 В **набора данных** сформированном **IsPrimaryKey** свойство **UniqueConstraint** присваивается **true** так как схемы Указывает `msdata:PrimaryKey="true"` в **ключ** элемент.  
  
 Значение **ConstraintName** свойство **UniqueConstraint** в **набора данных** значение **msdata: ConstraintName** атрибут, указанный в **ключ** элемента в схеме.  
  
## <a name="see-also"></a>См. также

- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
