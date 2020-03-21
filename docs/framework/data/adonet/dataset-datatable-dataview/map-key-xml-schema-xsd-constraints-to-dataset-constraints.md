---
title: Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150939"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме можно указать ограничение ключа на элементе или атрибуте с помощью **ключевого** элемента. Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.  
  
 Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.  
  
 В следующей таблице излагаются атрибуты **msdata,** которые можно указать в **ключевом** элементе.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае атрибут **имени** предоставляет значение имени сограничения.|  
|**msdata:PrimaryKey**|Если `PrimaryKey="true"` присутствует, свойство ограничения **IsPrimaryKey** настроено на **истину,** что делает его основным ключом. Свойство столбца **AllowDBNull** настроено на **ложное,** поскольку первичные ключи не могут иметь нулевых значений.|  
  
 При преобразовании схемы, в которой указывается ограничение ключа, процесс отображения создает уникальное ограничение на столе с свойством столбца **AllowDBNull,** установленным **для ложного** для каждого столбца в стаблене. Свойство **IsPrimaryKey** уникального ограничения также устанавливается на `msdata:PrimaryKey="true"` **ложное,** если вы не указали на **ключевом** элементе. Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.  
  
 В следующем примере схемы **ключевой** элемент определяет ключевое ограничение элемента **CustomerID.**  
  
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
  
 **Ключевой** элемент определяет, что значения элемента **CustomerID** ребенка **элемента Клиентов** должны иметь уникальные значения и не могут иметь нулевые значения. При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Отображение XML Schema также создает **UniqueConstraint** на столбце <xref:System.Data.DataSet> **CustomerID,** как показано в следующем. (Для простоты показаны только значимые свойства.)  
  
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
  
 В генерируемом **DataSet** свойство **IsPrimaryKey** **UniqueConstraint** верно, **поскольку** схема определяется `msdata:PrimaryKey="true"` в **ключевом** элементе.  
  
 Значение свойства **ConstraintName** **UniqueConstraint** в **DataSet** — это значение атрибута **msdata:ConstraintName,** указанного в **ключевом** элементе схемы.  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
