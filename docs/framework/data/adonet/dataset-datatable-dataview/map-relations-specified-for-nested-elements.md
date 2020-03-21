---
title: Сопоставление отношений, заданных для вложенных элементов
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150900"
---
# <a name="map-relations-specified-for-nested-elements"></a>Сопоставление отношений, заданных для вложенных элементов
Схема может включать аннотацию **msdata:Relationship** для явного указания отображения между любыми двумя элементами в схеме. Два элемента, указанные в **msdata:Relationship** могут быть вложены в схему, но не должны быть. Процесс отображения использует **msdata:Relationship** в схеме для создания основного ключевого/иностранного ключевого отношения между двумя столбиками.  
  
 Ниже приводится XML Schema, в которой элемент **OrderDetail** является элементом детского **заказа.** **Msdata:Relationship** определяет эти отношения между родителями и детьми и указывает, что столбец **OrderNumber** в результате **таблицы Заказа** связан с столбцом **OrderNo** в результирующей таблице **OrderDetail.**  
  
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
  
- **Таблица Заказа** и **заказаDetail.**  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Взаимосвязь между таблицами **Order** и **OrderDetail.** **Свойство Nested** для этого отношения настроено на **Истину,** потому что элементы **Заказа** и **ЗаказаDetail** вложены в схему.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Процесс сопоставления не создает никаких ограничений.  
  
## <a name="see-also"></a>См. также раздел

- [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
