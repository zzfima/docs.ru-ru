---
title: Ограничения и отношения схемы XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 47b1a3e81cfbc4eb58531b1633dd29becbe497a2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040031"
---
# <a name="xml-schema-constraints-and-relationships"></a>Ограничения и отношения схемы XML
В схеме языка определения схемы XML (XSD) можно указать ограничения (ограничения UNIQUE, Key и keyref) и отношения (с помощью аннотации **msdata: relationship** ). В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.  
  
 Как правило, в XML-схеме задается Аннотация **msdata: relationship** , если нужно создать только связи в **наборе данных**. Дополнительные сведения см. [в разделе Создание связей наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Если необходимо создать ограничения в **наборе данных**, необходимо указать ограничения (уникальные, ключ и keyref). Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Формирование связи из ограничений key и keyref  
 Вместо указания аннотации **msdata: relationship** можно указать ограничения key и keyref, которые используются в процессе СОПОСТАВЛЕНИЯ схем XML для создания не только ограничений, но и связи в **наборе данных**. Однако при указании `msdata:ConstraintOnly="true"` в элементе **keyref** **набор данных** будет включать только ограничения и не будет включать связь.  
  
 В следующем примере показана схема XML, включающая элементы **Order** и **OrderDetail** , которые не являются вложенными. Схема также указывает ограничения key и keyref.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 **Набор данных** , формируемый в процессе СОПОСТАВЛЕНИЯ схем XML, включает таблицы **Order** и **OrderDetail** . Кроме того, **набор данных** содержит отношения и ограничения. Эти связи и ограничения показаны в приведенном ниже примере. Обратите внимание, что в схеме не указана Аннотация **msdata: relationship** ; Вместо этого для создания отношения используются ограничения key и keyref.  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 В приведенном выше примере схемы элементы **Order** и **OrderDetail** не являются вложенными. В следующем примере схемы эти элементы являются вложенными. Однако Аннотация **msdata: relationship** не указана. Поэтому предполагается неявное отношение. Дополнительные сведения см. в разделе [Сопоставление неявных отношений между вложенными элементами схемы](map-implicit-relations-between-nested-schema-elements.md). Схема также указывает ограничения key и keyref.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 **Набор данных** , полученный из процесса СОПОСТАВЛЕНИЯ схем XML, включает две таблицы:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 **Набор данных** также содержит две связи (одна на основе аннотации **msdata: relationship** , а другая — на основе ограничений key и keyref) и различных ограничений. Эти связи и ограничения показаны в следующем примере.  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 Если ограничение keyref, ссылающееся на вложенную таблицу, содержит аннотацию **msdata: Nested = "true"** , **набор данных** создаст одну вложенную связь, основанную на ограничении keyref, и связанное ограничение UNIQUE/Key.  
  
## <a name="see-also"></a>См. также

- [Наследование реляционной структуры DataSet от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
