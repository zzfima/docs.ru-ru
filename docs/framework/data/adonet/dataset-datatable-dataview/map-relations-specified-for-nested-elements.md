---
title: Сопоставление отношений, заданных для вложенных элементов
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 138fbbc3ccaa90096a15fa87544e5c29f66beb08
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040065"
---
# <a name="map-relations-specified-for-nested-elements"></a>Сопоставление отношений, заданных для вложенных элементов
Схема может включать аннотацию **msdata: relationship** для явного указания сопоставления между любыми двумя элементами в схеме. Два элемента, указанные в **msdata: relationship** , могут быть вложены в схему, но не обязательно должны быть. Процесс сопоставления использует **msdata: relationship** в схеме для создания связи «первичный-внешний ключ» между двумя столбцами.  
  
 В следующем примере показана схема XML, в которой элемент **OrderDetail** является дочерним элементом **Order**. Элемент **msdata: relationship** определяет эту связь типа «родители-потомки» и указывает, что столбец **OrderNumber** результирующей таблицы **Order** связан со столбцом **ордерно** результирующей таблицы **OrderDetail** .  
  
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
  
- **Заказ** и таблица **OrderDetail** .  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Связь между таблицами **Order** и **OrderDetail** . **Вложенному** свойству для этой связи присваивается **значение true** , поскольку элементы **Order** и **OrderDetail** вложены в схему.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Процесс сопоставления не создает никаких ограничений.  
  
## <a name="see-also"></a>См. также

- [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
