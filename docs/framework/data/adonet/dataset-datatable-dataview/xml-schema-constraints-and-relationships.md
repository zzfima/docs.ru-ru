---
title: "Ограничения и отношения схемы XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e450954e4b0e51057e98dd329fe26c38f0ebbb05
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="6d0d1-102">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="6d0d1-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="6d0d1-103">Ограничения можно указать в схему языка определения схемы XML (unique, key и keyref) и связи (с помощью **msdata: Relationship** заметки).</span><span class="sxs-lookup"><span data-stu-id="6d0d1-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="6d0d1-104">В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="6d0d1-105">Как правило, в схеме XML указывается **msdata: Relationship** заметку, если вы хотите создать только связи в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="6d0d1-106">Дополнительные сведения см. в разделе [создание отношений наборов данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="6d0d1-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="6d0d1-107">Указать ограничения (unique, key и keyref) Если вы хотите создать ограничения в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="6d0d1-108">Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="6d0d1-109">Формирование связи из ограничений key и keyref</span><span class="sxs-lookup"><span data-stu-id="6d0d1-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="6d0d1-110">Вместо указания **msdata: Relationship** заметки, можно указать ограничения key и keyref, которые используются в процессе сопоставления схемы XML для создания не только ограничения, но и связи в  **Набор данных**.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="6d0d1-111">Тем не менее при указании `msdata:ConstraintOnly="true"` в **keyref** элемент, **DataSet** войдут только ограничения и не содержит связь.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="6d0d1-112">В следующем примере показано схемы XML, включающий **порядок** и **OrderDetail** элементы, которые не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="6d0d1-113">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="6d0d1-114">**DataSet** , создаваемый в процессе включает процесс сопоставления схемы XML **порядок** и **OrderDetail** таблиц.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="6d0d1-115">Кроме того **DataSet** входят связи и ограничения.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="6d0d1-116">Эти связи и ограничения показаны в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="6d0d1-117">Обратите внимание, что схема задает **msdata: Relationship** заметку; вместо этого ограничения key и keyref используются для создания связи.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
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
  
 <span data-ttu-id="6d0d1-118">В предыдущем примере схемы **порядок** и **OrderDetail** элементы не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="6d0d1-119">В следующем примере схемы эти элементы являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="6d0d1-120">Тем не менее не **msdata: Relationship** указана заметка; поэтому подразумевается неявная связь.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="6d0d1-121">Дополнительные сведения см. в разделе [неявные отношения между вложенным схемы элементов карты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6d0d1-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="6d0d1-122">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="6d0d1-123">**Набора данных** , полученных в результате сопоставления XML-схемы содержит две таблицы:</span><span class="sxs-lookup"><span data-stu-id="6d0d1-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="6d0d1-124">**DataSet** также содержит две связи (одну на основе **msdata: Relationship** заметки, а другой в зависимости от ограничений key и keyref) и различные ограничения.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="6d0d1-125">Эти связи и ограничения показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-125">The following example shows the relations and constraints.</span></span>  
  
```  
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
  
 <span data-ttu-id="6d0d1-126">Если ограничение keyref, ссылающиеся на вложенной таблицы содержит **msdata: IsNested = «true»** заметки, **DataSet** создаст одну вложенную связь на основании ограничения keyref и связанные ограничения unique/key.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d0d1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6d0d1-127">See Also</span></span>  
 [<span data-ttu-id="6d0d1-128">Наследование реляционной структуры DataSet от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6d0d1-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="6d0d1-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6d0d1-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
