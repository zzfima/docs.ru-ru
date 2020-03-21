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
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="eeb77-102">Сопоставление отношений, заданных для вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="eeb77-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="eeb77-103">Схема может включать аннотацию **msdata:Relationship** для явного указания отображения между любыми двумя элементами в схеме.</span><span class="sxs-lookup"><span data-stu-id="eeb77-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="eeb77-104">Два элемента, указанные в **msdata:Relationship** могут быть вложены в схему, но не должны быть.</span><span class="sxs-lookup"><span data-stu-id="eeb77-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="eeb77-105">Процесс отображения использует **msdata:Relationship** в схеме для создания основного ключевого/иностранного ключевого отношения между двумя столбиками.</span><span class="sxs-lookup"><span data-stu-id="eeb77-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="eeb77-106">Ниже приводится XML Schema, в которой элемент **OrderDetail** является элементом детского **заказа.**</span><span class="sxs-lookup"><span data-stu-id="eeb77-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="eeb77-107">**Msdata:Relationship** определяет эти отношения между родителями и детьми и указывает, что столбец **OrderNumber** в результате **таблицы Заказа** связан с столбцом **OrderNo** в результирующей таблице **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="eeb77-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="eeb77-108">Процесс сопоставления схем XML создает в объекте <xref:System.Data.DataSet> следующее.</span><span class="sxs-lookup"><span data-stu-id="eeb77-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="eeb77-109">**Таблица Заказа** и **заказаDetail.**</span><span class="sxs-lookup"><span data-stu-id="eeb77-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="eeb77-110">Взаимосвязь между таблицами **Order** и **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="eeb77-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="eeb77-111">**Свойство Nested** для этого отношения настроено на **Истину,** потому что элементы **Заказа** и **ЗаказаDetail** вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="eeb77-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="eeb77-112">Процесс сопоставления не создает никаких ограничений.</span><span class="sxs-lookup"><span data-stu-id="eeb77-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb77-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eeb77-113">See also</span></span>

- [<span data-ttu-id="eeb77-114">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="eeb77-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="eeb77-115">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="eeb77-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="eeb77-116">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eeb77-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
