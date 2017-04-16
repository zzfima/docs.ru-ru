---
title: "Сопоставление неявных связей между вложенными элементами схемы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление неявных связей между вложенными элементами схемы
Схема на языке XSD может иметь сложные типы, вложенные друг в друга.  В этом случае процесс сопоставления применяет сопоставление по умолчанию и создает в объекте <xref:System.Data.DataSet>:  
  
-   одну таблицу для каждого сложного типа \(родительского и дочернего\);  
  
-   один дополнительный столбец *TableName*\_Id в первичном ключе на каждое определение таблицы, где *TableName* — это имя родительской таблицы, если для родительской таблицы не существует ограничения уникальности;  
  
-   ограничение первичного ключа для родительской таблицы, определяющее дополнительный столбец как часть первичного ключа \(путем задания свойству **IsPrimaryKey** значения **True**\).  Ограничению назначается имя Constraint*\#*, где *\#* — это 1, 2, 3 и т. д.  Например, имя первого ограничения по умолчанию \- Constraint1;  
  
-   ограничение внешнего ключа для дочерней таблицы, определяющее дополнительный столбец как внешний ключ, ссылающийся на первичный ключ родительской таблицы.  Ограничение имеет имя *ParentTable\_ChildTable*, где *ParentTable* — это имя родительской таблицы, а *ChildTable* — это имя дочерней таблицы;  
  
-   связи данных между родительскими и дочерними таблицами.  
  
 В следующем примере показывается схема, где **OrderDetail** \- это дочерний элемент таблицы **Order**.  
  
```  
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
  
 Процесс сопоставления схемы XML создает в объекте **DataSet**:  
  
-   Таблицы **Order** и **OrderDetail**.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Ограничение уникальности на таблицу **Order**.  Отметим, что свойство **IsPrimaryKey** имеет значение **True**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Ограничение внешнего ключа на таблицу **OrderDetail**.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Связь между таблицами **Order** и **OrderDetail**.  Свойству **Nested** для данной связи устанавливается значение **True**, так как элементы **Order** и **OrderDetail** вложены в схему.  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## См. также  
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)