---
title: "Указание отношений между элементами без вложенности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 036085160e9e4817964754a85db627e4d4ba8654
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="ca806-102">Указание отношений между элементами без вложенности</span><span class="sxs-lookup"><span data-stu-id="ca806-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="ca806-103">Если элементы не вложены, какие-либо неявные связи не создаются.</span><span class="sxs-lookup"><span data-stu-id="ca806-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="ca806-104">Однако, можно явно указать связей между элементами, которые не являются вложенными с помощью **msdata: Relationship** заметки.</span><span class="sxs-lookup"><span data-stu-id="ca806-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="ca806-105">В следующем примере показано XML-схемы, в котором **msdata: Relationship** между указана заметка **порядок** и **OrderDetail** элементов, которые не являются вложенность.</span><span class="sxs-lookup"><span data-stu-id="ca806-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="ca806-106">**Msdata: Relationship** как дочерний элемент элемента задана заметка **схемы** элемента.</span><span class="sxs-lookup"><span data-stu-id="ca806-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="ca806-107">Процесс сопоставления схемы языка XSD определения схемы XML создает <xref:System.Data.DataSet> с **порядок** и **OrderDetail** таблиц и связь между этими двумя таблицами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ca806-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca806-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ca806-108">See Also</span></span>  
 [<span data-ttu-id="ca806-109">Создание отношений наборов данных из XML-схемы (XSD)</span><span class="sxs-lookup"><span data-stu-id="ca806-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="ca806-110">Сопоставление ограничений XML схемы (XSD) для ограничения набора данных</span><span class="sxs-lookup"><span data-stu-id="ca806-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="ca806-111">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ca806-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
