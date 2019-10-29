---
title: Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 6b847aba31aa75f7be3bd6a11b6bcb8231c06bc4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040361"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
В схеме языка определения схемы XML (XSD) элемент **UNIQUE** указывает ограничение уникальности для элемента или атрибута. В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.  
  
 В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **UNIQUE** .  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: ConstraintName**|Если этот атрибут указан, его значение используется в качестве имени ограничения. В противном случае атрибут **Name** предоставляет значение имени ограничения.|  
|**msdata: PrimaryKey**|Если `PrimaryKey="true"` содержится в элементе **UNIQUE** , то создается ограничение UNIQUE, в котором свойство **IsPrimaryKey имеют значение** имеет значение **true**.|  
  
 В следующем примере показана схема XML, использующая элемент **UNIQUE** для указания ограничения уникальности.  
  
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
  
 Элемент **UNIQUE** в схеме указывает, что для всех элементов **Customer** в экземпляре документа значение дочернего элемента **CustomerID** должно быть уникальным. При построении **набора данных**процесс сопоставления считывает эту схему и создает следующую таблицу:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Процесс сопоставления также создает ограничение UNIQUE для столбца **CustomerID** , как показано в следующем **наборе данных**. (Для простоты показаны только значимые свойства.)  
  
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
  
 В созданном **наборе данных** свойству **IsPrimaryKey имеют значение** присваивается **значение false** для ограничения UNIQUE. Свойство **UNIQUE** в столбце указывает, что значения столбца **CustomerID** должны быть уникальными (но могут быть пустой ссылкой, как указано свойством **AllowDbNull** столбца).  
  
 Если изменить схему и задать для необязательного значения атрибута **msdata: PrimaryKey** значение **true**, в таблице будет создано ограничение UNIQUE. Свойство **AllowDbNull** column имеет значение **false**, а свойство **IsPrimaryKey имеют значение** ограничения имеет значение **true**, что делает столбец **CustomerID** первичным ключевым столбцом.  
  
 Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML. В следующем примере показано, как указать, что сочетание значений **CustomerID** и **CompanyName** должно быть уникальным для всех **клиентов** в любом экземпляре путем добавления еще одного элемента **xs: field** в схему.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Это ограничение, создаваемое в результирующем **наборе данных**.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>См. также

- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
