---
title: Сопоставление неявных отношений между вложенными элементами схемы
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 73cd8a83021934de3b8e3bf494a4f59dd32e183c
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847410"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="14bc4-102">Сопоставление неявных отношений между вложенными элементами схемы</span><span class="sxs-lookup"><span data-stu-id="14bc4-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="14bc4-103">Схема на языке XSD может иметь сложные типы, вложенные друг в друга.</span><span class="sxs-lookup"><span data-stu-id="14bc4-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="14bc4-104">В этом случае процесс сопоставления применяет сопоставление по умолчанию и создает в объекте <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="14bc4-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="14bc4-105">одну таблицу для каждого сложного типа (родительского и дочернего);</span><span class="sxs-lookup"><span data-stu-id="14bc4-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="14bc4-106">Если не существует ограничения уникальности в родительском элементе, один дополнительный столбец первичного ключа на каждое определение таблицы с именем *TableName*_Id где *TableName* имя родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="14bc4-107">Ограничение первичного ключа в родительской таблице, определяющее дополнительный столбец как первичный ключ (задавая **IsPrimaryKey** свойства **True**).</span><span class="sxs-lookup"><span data-stu-id="14bc4-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="14bc4-108">Ограничению назначается имя Constraint\#, где \# - это 1, 2, 3 и т. д.</span><span class="sxs-lookup"><span data-stu-id="14bc4-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="14bc4-109">Например, имя первого ограничения по умолчанию - Constraint1;</span><span class="sxs-lookup"><span data-stu-id="14bc4-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="14bc4-110">ограничение внешнего ключа для дочерней таблицы, определяющее дополнительный столбец как внешний ключ, ссылающийся на первичный ключ родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="14bc4-111">Ограничению назначается имя *ParentTable_ChildTable* где *ParentTable* имя родительской таблицы и *ChildTable* — это имя дочерней таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="14bc4-112">связи данных между родительскими и дочерними таблицами.</span><span class="sxs-lookup"><span data-stu-id="14bc4-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="14bc4-113">В следующем примере показано схемы где **OrderDetail** является дочерним элементом элемента **порядок**.</span><span class="sxs-lookup"><span data-stu-id="14bc4-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="14bc4-114">Процесс сопоставления схем XML создает в **набора данных**:</span><span class="sxs-lookup"><span data-stu-id="14bc4-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="14bc4-115">**Порядок** и **OrderDetail** таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="14bc4-116">Ограничение уникальности на **порядок** таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="14bc4-117">Обратите внимание, что **IsPrimaryKey** свойству **True**.</span><span class="sxs-lookup"><span data-stu-id="14bc4-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="14bc4-118">Ограничение внешнего ключа для **OrderDetail** таблицы.</span><span class="sxs-lookup"><span data-stu-id="14bc4-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="14bc4-119">Отношение между **порядок** и **OrderDetail** таблиц.</span><span class="sxs-lookup"><span data-stu-id="14bc4-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="14bc4-120">**Nested** свойство для этой связи имеет значение **True** поскольку **порядок** и **OrderDetail** элементы вложены в схеме .</span><span class="sxs-lookup"><span data-stu-id="14bc4-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14bc4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="14bc4-121">See Also</span></span>  
 [<span data-ttu-id="14bc4-122">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="14bc4-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="14bc4-123">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="14bc4-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="14bc4-124">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14bc4-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
