---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150887"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="41c19-102">Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="41c19-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="41c19-103">Элемент **keyref** позволяет установить связи между элементами в документе.</span><span class="sxs-lookup"><span data-stu-id="41c19-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="41c19-104">Это похоже на связь по внешнему ключу в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="41c19-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="41c19-105">Если схема определяет элемент **keyref,** элемент преобразуется в процессе отображения схемы в соответствующее иностранное ограничение клавиш на <xref:System.Data.DataSet>столбцах в таблицах .</span><span class="sxs-lookup"><span data-stu-id="41c19-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="41c19-106">По умолчанию элемент **keyref** также генерирует отношение с **родительскими**свойствами, **ChildTable,** **ParentColumn**и **ChildColumn** свойствами, указанными в отношении.</span><span class="sxs-lookup"><span data-stu-id="41c19-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="41c19-107">В следующей таблице излагаются атрибуты **msdata,** которые можно указать в элементе **keyref.**</span><span class="sxs-lookup"><span data-stu-id="41c19-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="41c19-108">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="41c19-108">Attribute name</span></span>|<span data-ttu-id="41c19-109">Описание</span><span class="sxs-lookup"><span data-stu-id="41c19-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="41c19-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="41c19-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="41c19-111">Если **на** элементе keyref в схеме указан элемент **keyref,** создается ограничение, но никакое отношение не создается.</span><span class="sxs-lookup"><span data-stu-id="41c19-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="41c19-112">Если этот атрибут не указан (или установлен **на ложное),** как ограничение, так и отношение создаются в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="41c19-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="41c19-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="41c19-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="41c19-114">Если атрибут **ConstraintName** указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="41c19-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="41c19-115">В противном случае атрибут **имени** элемента **keyref** в схеме предоставляет имя ограничения в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="41c19-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="41c19-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="41c19-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="41c19-117">Если атрибут **UpdateRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **UpdateRule** в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="41c19-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41c19-118">В противном случае свойство **UpdateRule** настроено на **Каскад.**</span><span class="sxs-lookup"><span data-stu-id="41c19-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="41c19-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="41c19-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="41c19-120">Если атрибут **DeleteRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **DeleteRule** в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="41c19-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41c19-121">В противном случае свойство **DeleteRule** настроено на **Каскад.**</span><span class="sxs-lookup"><span data-stu-id="41c19-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="41c19-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="41c19-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="41c19-123">Если атрибут **AcceptRejectRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **AcceptRejectRule** в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="41c19-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41c19-124">В противном случае свойство **AcceptRejectRule** устанавливается **в Нет**.</span><span class="sxs-lookup"><span data-stu-id="41c19-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="41c19-125">Следующий пример содержит схему, которая определяет **ключевые** и **ключевые** отношения между элементом **ребенка OrderNumber** элемента **Порядка** и элементом **Ребенка OrderNo** элемента **Order** Of.</span><span class="sxs-lookup"><span data-stu-id="41c19-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="41c19-126">В примере элемент **«ПорядокНомер»** элемента **OrderDetail** относится к элементу **OrderNo** ключевого элемента ребенка **элемента Заказа.**</span><span class="sxs-lookup"><span data-stu-id="41c19-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="41c19-127">Процесс определения схемы XML Schema (XSD) создает следующий **DataSet** с двумя таблицами:</span><span class="sxs-lookup"><span data-stu-id="41c19-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="41c19-128">Кроме того, **DataSet** определяет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="41c19-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="41c19-129">Уникальное ограничение на столе **Заказа.**</span><span class="sxs-lookup"><span data-stu-id="41c19-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="41c19-130">Взаимосвязь между таблицами **Order** и **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="41c19-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="41c19-131">**Свойство Nested настроено** на **ложное,** поскольку два элемента не вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="41c19-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="41c19-132">Иностранное ограничение ключа на таблице **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="41c19-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41c19-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="41c19-133">See also</span></span>

- [<span data-ttu-id="41c19-134">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="41c19-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="41c19-135">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="41c19-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="41c19-136">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41c19-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
