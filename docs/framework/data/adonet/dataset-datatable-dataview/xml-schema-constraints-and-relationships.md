---
title: Ограничения и отношения схемы XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150718"
---
# <a name="xml-schema-constraints-and-relationships"></a>Ограничения и отношения схемы XML
В схеме определения xML Schema (XSD) можно указать ограничения (уникальные, ключевые и ключевые ограничения) и отношения (с помощью аннотации **msdata:Relationship).** В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.  
  
 Как правило, в XML Schema вы указываете аннотацию **msdata:Relationship,** если вы хотите генерировать только отношения в **DataSet.** Для получения дополнительной [информации](generating-dataset-relations-from-xml-schema-xsd.md)см. Вы указываете ограничения (уникальные, ключевые и keyref), если вы хотите создать ограничения в **DataSet.** Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Формирование связи из ограничений key и keyref  
 Вместо указания аннотации **msdata:Relationship** можно указать ограничения клавиш и ключей, которые используются в процессе картирования XML Schema для генерации не только ограничений, но и взаимосвязи в **DataSet.** Однако, если `msdata:ConstraintOnly="true"` вы укажете в элементе **keyref,** **DataSet** будет включать только ограничения и не будет включать в себя связь.  
  
 В следующем примере показана схема XML, которая включает элементы **Заказа** и **ЗаказаDetail,** которые не вложены. Схема также указывает ограничения key и keyref.  
  
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
  
 **DataSet,** генерируемый в процессе картирования XML Schema, включает таблицы **заказа** и **заказаDetail.** Кроме того, **DataSet** включает в себя отношения и ограничения. Эти связи и ограничения показаны в приведенном ниже примере. Обратите внимание, что в схеме не указана аннотация **msdata:Relationship;** вместо этого для создания связи используются ограничения клавиш и ключ.  
  
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
  
 В предыдущем примере схемы элементы **Заказа** и **ЗаказаDetail** не вложены. В следующем примере схемы эти элементы являются вложенными. Однако аннотация **msdata:Relationship** не указана; поэтому предполагается неявная связь. Для получения дополнительной информации [см. Карта неявные отношения между Nested Schema Элементы](map-implicit-relations-between-nested-schema-elements.md). Схема также указывает ограничения key и keyref.  
  
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
  
 **DataSet** в результате процесса картирования XML Schema включает в себя две таблицы:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 **DataSet** также включает в себя два отношения (один на основе **аннотации msdata:relationship,** а другой на основе ключевых и ключевых ограничений) и различные ограничения. Эти связи и ограничения показаны в следующем примере.  
  
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
  
 Если ограничение keyref, относящееся к вложенной таблице, содержит аннотацию **msdata:IsNested"true"** **DataSet** создаст единую вложенную связь, основанную на ограничении keyref и связанном с этим уникальном/ключевом ограничении.  
  
## <a name="see-also"></a>См. также раздел

- [Наследование реляционной структуры набора данных от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
