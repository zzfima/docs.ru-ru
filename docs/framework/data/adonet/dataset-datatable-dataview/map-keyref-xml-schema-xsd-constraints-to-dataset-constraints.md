---
title: "Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4ca72292bd2c43fec6f3833d521ddb83c01c32c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
**Keyref** элемент позволяет устанавливать ссылки между элементами внутри документа. Это похоже на связь по внешнему ключу в реляционной базе данных. Если в схеме **keyref** элемент преобразуется в процессе сопоставления схемы в соответствующие ограничения внешнего ключа на столбцы в таблицах с <xref:System.Data.DataSet>. По умолчанию **keyref** элемент также формирует связь с **ParentTable**, **ChildTable**, **ParentColumn**и  **ChildColumn** свойства, указанные в этой связи.  
  
 В следующей таблице описываются **msdata** атрибуты, можно указать в **keyref** элемента.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: constraintonly**|Если **ConstraintOnly = «true»** указано на **keyref** элемент в схеме, создается ограничение, но не создается связь. Если этот атрибут не указан (или имеет значение **False**), ограничения и связи, создаются в **набора данных**.|  
|**msdata: ConstraintName**|Если **ConstraintName** атрибут указан, его значение используется в качестве имени ограничения. В противном случае **имя** атрибут **keyref** элемент в схеме предоставляет имя ограничения в **набора данных**.|  
|**msdata:UpdateRule**|Если **UpdateRule** задан в **keyref** элемента в схеме, его значение будет назначено **UpdateRule** свойства ограничения в  **Набор данных**. В противном случае **UpdateRule** свойству **Cascade**.|  
|**msdata:DeleteRule**|Если **DeleteRule** задан в **keyref** элемента в схеме, его значение будет назначено **DeleteRule** свойства ограничения в  **Набор данных**. В противном случае **DeleteRule** свойству **Cascade**.|  
|**msdata:AcceptRejectRule**|Если **AcceptRejectRule** задан в **keyref** элемента в схеме, его значение будет назначено **AcceptRejectRule** свойства ограничения в  **Набор данных**. В противном случае **AcceptRejectRule** свойству **нет**.|  
  
 В следующем примере содержится схема, которая задает **ключ** и **keyref** связи между **OrderNumber** дочерний элемент элемента **заказа**  элемент и **OrderNo** дочерний элемент элемента **OrderDetail** элемента.  
  
 В примере **OrderNumber** дочерний элемент элемента **OrderDetail** ссылается на **OrderNo** ключа дочерний элемент элемента **порядок**элемент.  
  
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
  
 Процесс сопоставления схемы языка XSD определения схемы XML создает следующие **набора данных** с двумя таблицами:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Кроме того **DataSet** определяет следующие ограничения:  
  
-   Ограничение уникальности на **порядок** таблицы.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Связь между **порядок** и **OrderDetail** таблиц. **Nested** свойству **False** так, как два элемента не являются вложенными в схеме.  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   Ограничение внешнего ключа для **OrderDetail** таблицы.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>См. также  
 [Сопоставление ограничений XML схемы (XSD) для ограничения набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Создание отношений наборов данных из XML-схемы (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
