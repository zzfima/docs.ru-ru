---
title: Сопоставление неявных отношений между вложенными элементами схемы
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150967"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="ad590-102">Сопоставление неявных отношений между вложенными элементами схемы</span><span class="sxs-lookup"><span data-stu-id="ad590-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="ad590-103">Схема на языке XSD может иметь сложные типы, вложенные друг в друга.</span><span class="sxs-lookup"><span data-stu-id="ad590-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="ad590-104">В этом случае процесс сопоставления применяет сопоставление по умолчанию и создает в объекте <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="ad590-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="ad590-105">одну таблицу для каждого сложного типа (родительского и дочернего);</span><span class="sxs-lookup"><span data-stu-id="ad590-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="ad590-106">Если на родительском элементе не существует уникального ограничения, еще один основной столбец основного ключа в определении таблицы под названием *TableName*_Id где *TableName* — это имя родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="ad590-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="ad590-107">Основное ограничение ключа на родительской таблице, определяющее дополнительный столбец в качестве основного ключа (установив свойство **IsPrimaryKey** на **True).**</span><span class="sxs-lookup"><span data-stu-id="ad590-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="ad590-108">Ограничению назначается имя Constraint\#, где \# - это 1, 2, 3 и т. д.</span><span class="sxs-lookup"><span data-stu-id="ad590-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="ad590-109">Например, имя первого ограничения по умолчанию - Constraint1;</span><span class="sxs-lookup"><span data-stu-id="ad590-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="ad590-110">ограничение внешнего ключа для дочерней таблицы, определяющее дополнительный столбец как внешний ключ, ссылающийся на первичный ключ родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="ad590-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="ad590-111">Ограничение называется *ParentTable_ChildTable* где *ParentTable* — это название родительской таблицы, а *ChildTable* — название таблицы детей.</span><span class="sxs-lookup"><span data-stu-id="ad590-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="ad590-112">связи данных между родительскими и дочерними таблицами.</span><span class="sxs-lookup"><span data-stu-id="ad590-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="ad590-113">Ниже приводится схема, в которой **OrderDetail** является элементом детского **заказа.**</span><span class="sxs-lookup"><span data-stu-id="ad590-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="ad590-114">Процесс картирования XML Schema создает следующее в **DataSet:**</span><span class="sxs-lookup"><span data-stu-id="ad590-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="ad590-115">**Таблица Заказа** и **заказаDetail.**</span><span class="sxs-lookup"><span data-stu-id="ad590-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="ad590-116">Уникальное ограничение на столе **Заказа.**</span><span class="sxs-lookup"><span data-stu-id="ad590-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="ad590-117">Обратите внимание, что свойство **IsPrimaryKey** настроено на **True.**</span><span class="sxs-lookup"><span data-stu-id="ad590-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="ad590-118">Иностранное ограничение ключа на таблице **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="ad590-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- <span data-ttu-id="ad590-119">Взаимосвязь между таблицами **Order** и **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="ad590-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="ad590-120">**Свойство Nested** для этого отношения настроено на **Истину,** потому что элементы **Заказа** и **ЗаказаDetail** вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="ad590-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ad590-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ad590-121">See also</span></span>

- [<span data-ttu-id="ad590-122">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="ad590-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="ad590-123">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="ad590-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="ad590-124">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad590-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
