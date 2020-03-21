---
title: Ограничения и отношения схемы XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150718"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="f5e89-102">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="f5e89-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="f5e89-103">В схеме определения xML Schema (XSD) можно указать ограничения (уникальные, ключевые и ключевые ограничения) и отношения (с помощью аннотации **msdata:Relationship).**</span><span class="sxs-lookup"><span data-stu-id="f5e89-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="f5e89-104">В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f5e89-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="f5e89-105">Как правило, в XML Schema вы указываете аннотацию **msdata:Relationship,** если вы хотите генерировать только отношения в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="f5e89-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="f5e89-106">Для получения дополнительной [информации](generating-dataset-relations-from-xml-schema-xsd.md)см.</span><span class="sxs-lookup"><span data-stu-id="f5e89-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="f5e89-107">Вы указываете ограничения (уникальные, ключевые и keyref), если вы хотите создать ограничения в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="f5e89-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="f5e89-108">Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.</span><span class="sxs-lookup"><span data-stu-id="f5e89-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="f5e89-109">Формирование связи из ограничений key и keyref</span><span class="sxs-lookup"><span data-stu-id="f5e89-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="f5e89-110">Вместо указания аннотации **msdata:Relationship** можно указать ограничения клавиш и ключей, которые используются в процессе картирования XML Schema для генерации не только ограничений, но и взаимосвязи в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="f5e89-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="f5e89-111">Однако, если `msdata:ConstraintOnly="true"` вы укажете в элементе **keyref,** **DataSet** будет включать только ограничения и не будет включать в себя связь.</span><span class="sxs-lookup"><span data-stu-id="f5e89-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="f5e89-112">В следующем примере показана схема XML, которая включает элементы **Заказа** и **ЗаказаDetail,** которые не вложены.</span><span class="sxs-lookup"><span data-stu-id="f5e89-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="f5e89-113">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="f5e89-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="f5e89-114">**DataSet,** генерируемый в процессе картирования XML Schema, включает таблицы **заказа** и **заказаDetail.**</span><span class="sxs-lookup"><span data-stu-id="f5e89-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="f5e89-115">Кроме того, **DataSet** включает в себя отношения и ограничения.</span><span class="sxs-lookup"><span data-stu-id="f5e89-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="f5e89-116">Эти связи и ограничения показаны в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="f5e89-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="f5e89-117">Обратите внимание, что в схеме не указана аннотация **msdata:Relationship;** вместо этого для создания связи используются ограничения клавиш и ключ.</span><span class="sxs-lookup"><span data-stu-id="f5e89-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="f5e89-118">В предыдущем примере схемы элементы **Заказа** и **ЗаказаDetail** не вложены.</span><span class="sxs-lookup"><span data-stu-id="f5e89-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="f5e89-119">В следующем примере схемы эти элементы являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="f5e89-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="f5e89-120">Однако аннотация **msdata:Relationship** не указана; поэтому предполагается неявная связь.</span><span class="sxs-lookup"><span data-stu-id="f5e89-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="f5e89-121">Для получения дополнительной информации [см. Карта неявные отношения между Nested Schema Элементы](map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e89-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="f5e89-122">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="f5e89-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="f5e89-123">**DataSet** в результате процесса картирования XML Schema включает в себя две таблицы:</span><span class="sxs-lookup"><span data-stu-id="f5e89-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="f5e89-124">**DataSet** также включает в себя два отношения (один на основе **аннотации msdata:relationship,** а другой на основе ключевых и ключевых ограничений) и различные ограничения.</span><span class="sxs-lookup"><span data-stu-id="f5e89-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="f5e89-125">Эти связи и ограничения показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f5e89-125">The following example shows the relations and constraints.</span></span>  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="f5e89-126">Если ограничение keyref, относящееся к вложенной таблице, содержит аннотацию **msdata:IsNested"true"** **DataSet** создаст единую вложенную связь, основанную на ограничении keyref и связанном с этим уникальном/ключевом ограничении.</span><span class="sxs-lookup"><span data-stu-id="f5e89-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e89-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5e89-127">See also</span></span>

- [<span data-ttu-id="f5e89-128">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f5e89-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="f5e89-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5e89-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
