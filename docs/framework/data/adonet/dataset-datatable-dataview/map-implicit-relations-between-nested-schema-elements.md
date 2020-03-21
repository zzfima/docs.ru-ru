---
title: Сопоставление неявных отношений между вложенными элементами схемы
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150967"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Сопоставление неявных отношений между вложенными элементами схемы
Схема на языке XSD может иметь сложные типы, вложенные друг в друга. В этом случае процесс сопоставления применяет сопоставление по умолчанию и создает в объекте <xref:System.Data.DataSet>:  
  
- одну таблицу для каждого сложного типа (родительского и дочернего);  
  
- Если на родительском элементе не существует уникального ограничения, еще один основной столбец основного ключа в определении таблицы под названием *TableName*_Id где *TableName* — это имя родительской таблицы.  
  
- Основное ограничение ключа на родительской таблице, определяющее дополнительный столбец в качестве основного ключа (установив свойство **IsPrimaryKey** на **True).** Ограничению назначается имя Constraint\#, где \# - это 1, 2, 3 и т. д. Например, имя первого ограничения по умолчанию - Constraint1;  
  
- ограничение внешнего ключа для дочерней таблицы, определяющее дополнительный столбец как внешний ключ, ссылающийся на первичный ключ родительской таблицы. Ограничение называется *ParentTable_ChildTable* где *ParentTable* — это название родительской таблицы, а *ChildTable* — название таблицы детей.  
  
- связи данных между родительскими и дочерними таблицами.  
  
 Ниже приводится схема, в которой **OrderDetail** является элементом детского **заказа.**  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 Процесс картирования XML Schema создает следующее в **DataSet:**  
  
- **Таблица Заказа** и **заказаDetail.**  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Уникальное ограничение на столе **Заказа.** Обратите внимание, что свойство **IsPrimaryKey** настроено на **True.**  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- Иностранное ограничение ключа на таблице **OrderDetail.**  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- Взаимосвязь между таблицами **Order** и **OrderDetail.** **Свойство Nested** для этого отношения настроено на **Истину,** потому что элементы **Заказа** и **ЗаказаDetail** вложены в схему.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
