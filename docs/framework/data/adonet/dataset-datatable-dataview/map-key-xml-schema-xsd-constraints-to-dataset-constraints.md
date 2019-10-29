---
title: Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 670c07dd83e880b79c1ccf0c5af00d253b83f827
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040077"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме можно указать ограничение ключа для элемента или атрибута с помощью элемента **Key** . Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.  
  
 Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.  
  
 В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **Key** .  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае атрибут **Name** предоставляет значение имени ограничения.|  
|**msdata: PrimaryKey**|Если имеется `PrimaryKey="true"`, свойство Constraint **IsPrimaryKey имеют значение** имеет значение **true**, делая его первичным ключом. Свойство **AllowDbNull** column имеет значение **false**, так как первичные ключи не могут иметь значения NULL.|  
  
 При преобразовании схемы, в которой указано ограничение по ключу, в процессе сопоставления создается ограничение уникальности для таблицы со свойством **AllowDbNull** столбца, установленным в **значение false** для каждого столбца в ограничении. Свойство **IsPrimaryKey имеют значение** ограничения UNIQUE также имеет значение **false** , если в элементе **Key** не указано `msdata:PrimaryKey="true"`. Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.  
  
 В следующем примере схемы элемент **Key** указывает ограничение ключа для элемента **CustomerID** .  
  
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
  
 Элемент **Key** указывает, что значения дочернего элемента **CustomerID** элемента **Customers** должны иметь уникальные значения и не могут иметь значения NULL. При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Сопоставление схемы XML также создает **UniqueConstraint** в столбце **CustomerID** , как показано в следующем <xref:System.Data.DataSet>. (Для простоты показаны только значимые свойства.)  
  
```text  
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
  
 В созданном **наборе данных** свойству **IsPrimaryKey имеют значение** **UniqueConstraint** присваивается **значение true** , поскольку схема определяет `msdata:PrimaryKey="true"` в элементе **Key** .  
  
 Значением свойства **ConstraintName** объекта **UniqueConstraint** в **наборе данных** является значение атрибута **msdata: ConstraintName** , указанного в элементе **Key** схемы.  
  
## <a name="see-also"></a>См. также

- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
