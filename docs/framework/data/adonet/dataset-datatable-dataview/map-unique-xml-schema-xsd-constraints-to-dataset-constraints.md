---
title: Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150848"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме определения XML Schema (XSD) **уникальный** элемент определяет ограничение уникальности элемента или атрибута. В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.  
  
 В следующей таблице излагаются атрибуты **msdata,** которые можно указать в **уникальном** элементе.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае атрибут **имени** предоставляет значение имени сограничения.|  
|**msdata:PrimaryKey**|Если `PrimaryKey="true"` присутствует в **уникальном** элементе, создается уникальное ограничение с свойством **IsPrimaryKey,** установленным на **истину.**|  
  
 В следующем примере показана схема XML, используюметодная **схема** для определения ограничения уникальности.  
  
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
  
 **Уникальный** элемент в схеме определяет, что для всех элементов **Заказчика** в экземпляре документа значение элемента child **CustomerID** должно быть уникальным. При создании **DataSet**процесс отображения считывает эту схему и генерирует следующую таблицу:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Процесс отображения также создает уникальное ограничение на столбец **CustomerID,** как показано в следующем **DataSet.** (Для простоты показаны только значимые свойства.)  
  
```text  
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
  
 В генерируемом **DataSet** свойство **IsPrimaryKey** настроено **на ложное** для уникального ограничения. **Уникальное** свойство на столбце указывает на то, что значения столбца **CustomerID** должны быть уникальными (но они могут быть нулевой ссылкой, указанной свойством **allowDBNull** столбца).  
  
 Если вы измените схему и установите дополнительное значение атрибута **msdata:PrimaryKey** на **True,** уникальное ограничение создается на столе. Свойство столбца **AllowDBNull** настроено на **ложное**свойство, а свойство **IsPrimaryKey** ограничения, установленного на **True,** тем самым делая столбец **CustomerID** основным ключевым столбцом.  
  
 Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML. В следующем примере показано, как указать, что сочетание значений **CustomerID** и **CompanyName** должно быть уникальным для всех **Клиентов** в любом случае, добавив другой элемент **xs:field** в схему.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 Это ограничение, которое создается в полученном **DataSet.**  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
