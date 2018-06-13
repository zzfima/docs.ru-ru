---
title: Сопоставление отношений, заданных для вложенных элементов
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e1fde0ef585621a6821838613a7e77dedf7042b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756700"
---
# <a name="map-relations-specified-for-nested-elements"></a>Сопоставление отношений, заданных для вложенных элементов
Схема может включать **msdata: Relationship** заметки, чтобы явно указать сопоставление между двумя элементами схемы. Два элемента, указанного в **msdata: Relationship** могут быть вложенными в схеме, но не обязательно. Процесс сопоставления использует **msdata: Relationship** в схеме для создания первичного ключа и внешнего ключа связи между двумя столбцами.  
  
 В следующем примере показано XML-схемы, в котором **OrderDetail** элемент является дочерним для элемента **порядок**. **Msdata: Relationship** определяет эту связь родитель потомок и указывает, что **OrderNumber** столбец результата **порядок** таблица связана с **OrderNo** столбец результата **OrderDetail** таблицы.  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 Процесс сопоставления схем XML создает в объекте <xref:System.Data.DataSet> следующее.  
  
-   **Порядок** и **OrderDetail** таблицы.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Связь между **порядок** и **OrderDetail** таблиц. **Nested** для этого отношения свойству **True** из-за **порядок** и **OrderDetail** элементы являются вложенными в схеме .  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Процесс сопоставления не создает никаких ограничений.  
  
## <a name="see-also"></a>См. также  
 [Создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
