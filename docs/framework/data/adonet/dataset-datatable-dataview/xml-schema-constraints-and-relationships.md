---
title: Ограничения и отношения схемы XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 47b1a3e81cfbc4eb58531b1633dd29becbe497a2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040031"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="47a14-102">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="47a14-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="47a14-103">В схеме языка определения схемы XML (XSD) можно указать ограничения (ограничения UNIQUE, Key и keyref) и отношения (с помощью аннотации **msdata: relationship** ).</span><span class="sxs-lookup"><span data-stu-id="47a14-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="47a14-104">В этом разделе описана интерпретация ограничений и связей, указанных в схеме XML, при формировании набора данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="47a14-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="47a14-105">Как правило, в XML-схеме задается Аннотация **msdata: relationship** , если нужно создать только связи в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="47a14-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="47a14-106">Дополнительные сведения см. [в разделе Создание связей наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="47a14-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="47a14-107">Если необходимо создать ограничения в **наборе данных**, необходимо указать ограничения (уникальные, ключ и keyref).</span><span class="sxs-lookup"><span data-stu-id="47a14-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="47a14-108">Обратите внимание, что ограничения key и keyref используются также для формирования связей, как объясняется далее в подразделе.</span><span class="sxs-lookup"><span data-stu-id="47a14-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="47a14-109">Формирование связи из ограничений key и keyref</span><span class="sxs-lookup"><span data-stu-id="47a14-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="47a14-110">Вместо указания аннотации **msdata: relationship** можно указать ограничения key и keyref, которые используются в процессе СОПОСТАВЛЕНИЯ схем XML для создания не только ограничений, но и связи в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="47a14-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="47a14-111">Однако при указании `msdata:ConstraintOnly="true"` в элементе **keyref** **набор данных** будет включать только ограничения и не будет включать связь.</span><span class="sxs-lookup"><span data-stu-id="47a14-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="47a14-112">В следующем примере показана схема XML, включающая элементы **Order** и **OrderDetail** , которые не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="47a14-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="47a14-113">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="47a14-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="47a14-114">**Набор данных** , формируемый в процессе СОПОСТАВЛЕНИЯ схем XML, включает таблицы **Order** и **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="47a14-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="47a14-115">Кроме того, **набор данных** содержит отношения и ограничения.</span><span class="sxs-lookup"><span data-stu-id="47a14-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="47a14-116">Эти связи и ограничения показаны в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="47a14-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="47a14-117">Обратите внимание, что в схеме не указана Аннотация **msdata: relationship** ; Вместо этого для создания отношения используются ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="47a14-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
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
  
 <span data-ttu-id="47a14-118">В приведенном выше примере схемы элементы **Order** и **OrderDetail** не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="47a14-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="47a14-119">В следующем примере схемы эти элементы являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="47a14-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="47a14-120">Однако Аннотация **msdata: relationship** не указана. Поэтому предполагается неявное отношение.</span><span class="sxs-lookup"><span data-stu-id="47a14-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="47a14-121">Дополнительные сведения см. в разделе [Сопоставление неявных отношений между вложенными элементами схемы](map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="47a14-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="47a14-122">Схема также указывает ограничения key и keyref.</span><span class="sxs-lookup"><span data-stu-id="47a14-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="47a14-123">**Набор данных** , полученный из процесса СОПОСТАВЛЕНИЯ схем XML, включает две таблицы:</span><span class="sxs-lookup"><span data-stu-id="47a14-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="47a14-124">**Набор данных** также содержит две связи (одна на основе аннотации **msdata: relationship** , а другая — на основе ограничений key и keyref) и различных ограничений.</span><span class="sxs-lookup"><span data-stu-id="47a14-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="47a14-125">Эти связи и ограничения показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="47a14-125">The following example shows the relations and constraints.</span></span>  
  
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
  
 <span data-ttu-id="47a14-126">Если ограничение keyref, ссылающееся на вложенную таблицу, содержит аннотацию **msdata: Nested = "true"** , **набор данных** создаст одну вложенную связь, основанную на ограничении keyref, и связанное ограничение UNIQUE/Key.</span><span class="sxs-lookup"><span data-stu-id="47a14-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a14-127">См. также</span><span class="sxs-lookup"><span data-stu-id="47a14-127">See also</span></span>

- [<span data-ttu-id="47a14-128">Наследование реляционной структуры DataSet от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="47a14-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="47a14-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47a14-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
