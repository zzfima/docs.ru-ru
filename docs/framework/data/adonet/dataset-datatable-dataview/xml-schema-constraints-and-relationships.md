---
title: Ограничения и отношения схемы XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: bcb6e257a40040701612b73768a98e056bccd6c5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872349"
---
# <a name="xml-schema-constraints-and-relationships"></a>Ограничения и отношения схемы XML
В схему языка определения схемы XML, можно указать ограничения (unique, key и keyref) и связи (с помощью **msdata: Relationship** заметки). В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.  
  
 Как правило, в схеме XML указывается **msdata: Relationship** заметки, если вы хотите создать только связи в **набора данных**. Дополнительные сведения см. в разделе [создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md). Задать ограничения (unique, key и keyref) Если вы хотите создать ограничения в **набора данных**. Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Формирование связи из ограничений key и keyref  
 Вместо указания **msdata: Relationship** заметки, можно указать ограничения key и keyref, которые используются в процессе сопоставления схемы XML для создания не только ограничения, но и связи в  **Набор данных**. Тем не менее если указать `msdata:ConstraintOnly="true"` в **keyref** элемент, **набора данных** войдут только ограничения и не будет включать связь.  
  
 В следующем примере показано схему XML, который включает в себя **порядок** и **OrderDetail** элементы, которые не являются вложенными. Схема также указывает ограничения key и keyref.  
  
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
  
 **Набора данных** , созданный во время включает в себя процесс сопоставления схемы XML **порядок** и **OrderDetail** таблиц. Кроме того **набора данных** входят связи и ограничения. Эти связи и ограничения показаны в приведенном ниже примере. Обратите внимание, что схема задает **msdata: Relationship** заметки; вместо этого ограничения key и keyref используются для создания связи.  
  
```  
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
  
 В предыдущем примере схемы **порядок** и **OrderDetail** элементы не являются вложенными. В следующем примере схемы эти элементы являются вложенными. Тем не менее не **msdata: Relationship** заметки указана, поэтому подразумевается неявная связь. Дополнительные сведения см. в разделе [неявных отношений между вложенными схемы элементов карты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md). Схема также указывает ограничения key и keyref.  
  
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
  
 **Набора данных** полученный в результате процесс сопоставления схемы XML, содержит две таблицы:  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 **Набора данных** также содержит две связи (на основе **msdata: Relationship** заметки, а другой — в зависимости от ограничений key и keyref) и различные ограничения. Эти связи и ограничения показаны в следующем примере.  
  
```  
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
  
 Если ограничение keyref, ссылающееся на вложенную таблицу содержит **msdata: IsNested = «true»** заметки, **набора данных** создаст одну вложенную связь на основании ограничения keyref и связанные ограничения unique/key.  
  
## <a name="see-also"></a>См. также  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
