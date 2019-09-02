---
title: Сопоставление отношений, заданных для вложенных элементов
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 510a5e676df7bac274c6086b94e9a23e7540da20
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204633"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="5a17a-102">Сопоставление отношений, заданных для вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="5a17a-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="5a17a-103">Схема может включать аннотацию **msdata: relationship** для явного указания сопоставления между любыми двумя элементами в схеме.</span><span class="sxs-lookup"><span data-stu-id="5a17a-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="5a17a-104">Два элемента, указанные в **msdata: relationship** , могут быть вложены в схему, но не обязательно должны быть.</span><span class="sxs-lookup"><span data-stu-id="5a17a-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="5a17a-105">Процесс сопоставления использует **msdata: relationship** в схеме для создания связи «первичный-внешний ключ» между двумя столбцами.</span><span class="sxs-lookup"><span data-stu-id="5a17a-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="5a17a-106">В следующем примере показана схема XML, в которой элемент **OrderDetail** является дочерним элементом **Order**.</span><span class="sxs-lookup"><span data-stu-id="5a17a-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="5a17a-107">Элемент **msdata: relationship** определяет эту связь типа «родители-потомки» и указывает, что столбец **OrderNumber** результирующей таблицы **Order** связан со столбцом **ордерно** результирующей таблицы **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="5a17a-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="5a17a-108">Процесс сопоставления схем XML создает в объекте <xref:System.Data.DataSet> следующее.</span><span class="sxs-lookup"><span data-stu-id="5a17a-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="5a17a-109">**Заказ** и таблица **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="5a17a-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="5a17a-110">Связь между таблицами **Order** и **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="5a17a-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="5a17a-111">**Вложенному** свойству для этой связи присваивается **значение true** , поскольку элементы **Order** и **OrderDetail** вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="5a17a-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="5a17a-112">Процесс сопоставления не создает никаких ограничений.</span><span class="sxs-lookup"><span data-stu-id="5a17a-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a17a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a17a-113">See also</span></span>

- [<span data-ttu-id="5a17a-114">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="5a17a-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="5a17a-115">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="5a17a-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="5a17a-116">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5a17a-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
