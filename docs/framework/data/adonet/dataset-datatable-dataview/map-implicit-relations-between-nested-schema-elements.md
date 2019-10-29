---
title: Сопоставление неявных отношений между вложенными элементами схемы
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 25fc2c427727273038f7b4267376d6ba6446b811
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040391"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Сопоставление неявных отношений между вложенными элементами схемы
Схема на языке XSD может иметь сложные типы, вложенные друг в друга. В этом случае процесс сопоставления применяет сопоставление по умолчанию и создает в объекте <xref:System.Data.DataSet>:  
  
- одну таблицу для каждого сложного типа (родительского и дочернего);  
  
- Если для родителя не существует ограничений UNIQUE, по одному дополнительному первичному ключевому столбцу для определения таблицы с именем *TableName*_Id, где *TableName* — это имя родительской таблицы.  
  
- Ограничение первичного ключа в родительской таблице, определяющее дополнительный столбец в качестве первичного ключа (путем присвоения свойству **IsPrimaryKey имеют значение** значения **true**). Ограничению назначается имя Constraint\#, где \# - это 1, 2, 3 и т. д. Например, имя первого ограничения по умолчанию - Constraint1;  
  
- ограничение внешнего ключа для дочерней таблицы, определяющее дополнительный столбец как внешний ключ, ссылающийся на первичный ключ родительской таблицы. Ограничение называется *ParentTable_ChildTable* , где *паренттабле* — имя родительской таблицы, а *ChildTable* — имя дочерней таблицы.  
  
- связи данных между родительскими и дочерними таблицами.  
  
 В следующем примере показана схема, в которой **OrderDetail** является дочерним элементом **Order**.  
  
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
  
 Процесс сопоставления схем XML создает в **наборе данных**следующее:  
  
- **Заказ** и таблица **OrderDetail** .  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Ограничение UNIQUE для таблицы **Order** . Обратите внимание, что свойство **IsPrimaryKey имеют значение** имеет значение **true**.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- Ограничение внешнего ключа для таблицы **OrderDetail** .  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- Связь между таблицами **Order** и **OrderDetail** . **Вложенному** свойству для этой связи присваивается **значение true** , поскольку элементы **Order** и **OrderDetail** вложены в схему.  
  
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
  
## <a name="see-also"></a>См. также

- [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
