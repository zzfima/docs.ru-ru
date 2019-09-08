---
title: Указание отношений между элементами без вложенности
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: d6cd6f04a9fdeafe7c419b40023af6c71d553ac7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784278"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="2af47-102">Указание отношений между элементами без вложенности</span><span class="sxs-lookup"><span data-stu-id="2af47-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="2af47-103">Если элементы не вложены, какие-либо неявные связи не создаются.</span><span class="sxs-lookup"><span data-stu-id="2af47-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="2af47-104">Однако можно явно указать связи между элементами, которые не вложены с помощью аннотации **msdata: relationship** .</span><span class="sxs-lookup"><span data-stu-id="2af47-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="2af47-105">В следующем примере показана схема XML, в которой заметка **msdata: relationship** задается между элементами **Order** и **OrderDetail** , которые не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="2af47-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="2af47-106">Аннотация **msdata: relationship** указывается как дочерний элемент элемента **Schema** .</span><span class="sxs-lookup"><span data-stu-id="2af47-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="2af47-107">В процессе сопоставления схемы языка определения схемы XML (XSD) создаются <xref:System.Data.DataSet> таблицы **Order** и **OrderDetail** и связь, указанная между этими двумя таблицами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2af47-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="2af47-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2af47-108">See also</span></span>

- [<span data-ttu-id="2af47-109">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="2af47-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="2af47-110">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="2af47-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="2af47-111">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2af47-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
