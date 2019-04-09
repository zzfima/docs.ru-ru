---
title: Сопоставление отношений, заданных для вложенных элементов
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 9772f077991c758be65bbb44b9474f1ad341371f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203149"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="b51b4-102">Сопоставление отношений, заданных для вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="b51b4-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="b51b4-103">Схема может включать **msdata: Relationship** заметки, чтобы явно указать сопоставление между двумя элементами в схеме.</span><span class="sxs-lookup"><span data-stu-id="b51b4-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="b51b4-104">Два элемента, указанного в **msdata: Relationship** могут быть вложенными в схеме, но не обязательно.</span><span class="sxs-lookup"><span data-stu-id="b51b4-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="b51b4-105">Процесс сопоставления использует **msdata: Relationship** в схеме для создания первичного ключа/связи по внешнему ключу между двумя столбцами.</span><span class="sxs-lookup"><span data-stu-id="b51b4-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="b51b4-106">В следующем примере показано XML-схемы, в котором **OrderDetail** элемент является дочерним элементом элемента **порядок**.</span><span class="sxs-lookup"><span data-stu-id="b51b4-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="b51b4-107">**Msdata: Relationship** определяет эту связь родитель потомок и указывает, что **OrderNumber** столбец результата **порядок** таблица связана с **OrderNo** столбец результата **OrderDetail** таблицы.</span><span class="sxs-lookup"><span data-stu-id="b51b4-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="b51b4-108">Процесс сопоставления схем XML создает в объекте <xref:System.Data.DataSet> следующее.</span><span class="sxs-lookup"><span data-stu-id="b51b4-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="b51b4-109">**Порядок** и **OrderDetail** таблицы.</span><span class="sxs-lookup"><span data-stu-id="b51b4-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="b51b4-110">Отношение между **порядок** и **OrderDetail** таблиц.</span><span class="sxs-lookup"><span data-stu-id="b51b4-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="b51b4-111">**Nested** свойство для этой связи имеет значение **True** поскольку **порядок** и **OrderDetail** элементы вложены в схеме .</span><span class="sxs-lookup"><span data-stu-id="b51b4-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="b51b4-112">Процесс сопоставления не создает никаких ограничений.</span><span class="sxs-lookup"><span data-stu-id="b51b4-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51b4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b51b4-113">See also</span></span>

- [<span data-ttu-id="b51b4-114">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b51b4-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="b51b4-115">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="b51b4-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="b51b4-116">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="b51b4-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
