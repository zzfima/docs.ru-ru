---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: b5ffe69886b08903feab4373b1cd5c5244b3b3b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784510"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="f11f2-102">Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="f11f2-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="f11f2-103">Элемент **keyref** позволяет устанавливать связи между элементами в документе.</span><span class="sxs-lookup"><span data-stu-id="f11f2-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="f11f2-104">Это похоже на связь по внешнему ключу в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="f11f2-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="f11f2-105">Если схема указывает элемент **keyref** , элемент преобразуется в процессе сопоставления схемы в соответствующее ограничение FOREIGN KEY для столбцов в таблицах <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f11f2-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f11f2-106">По умолчанию элемент **keyref** также создает отношение со свойствами **паренттабле**, **ChildTable**, **парентколумн**и **чилдколумн** , указанными для отношения.</span><span class="sxs-lookup"><span data-stu-id="f11f2-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="f11f2-107">В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **keyref** .</span><span class="sxs-lookup"><span data-stu-id="f11f2-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="f11f2-108">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="f11f2-108">Attribute name</span></span>|<span data-ttu-id="f11f2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f11f2-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f11f2-110">**msdata: Констраинтонли**</span><span class="sxs-lookup"><span data-stu-id="f11f2-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="f11f2-111">Если для элемента **keyref** схемы задано **значение констраинтонли = "true"** , то создается ограничение, но связь не создается.</span><span class="sxs-lookup"><span data-stu-id="f11f2-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="f11f2-112">Если этот атрибут не задан (или имеет значение **false**), в **наборе данных**создается и ограничение, и отношение.</span><span class="sxs-lookup"><span data-stu-id="f11f2-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="f11f2-113">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="f11f2-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="f11f2-114">Если указан атрибут **ConstraintName** , его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="f11f2-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="f11f2-115">В противном случае атрибут **Name** элемента **keyref** в схеме предоставляет имя ограничения в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="f11f2-116">**msdata: UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="f11f2-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="f11f2-117">Если атрибут **UpdateRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **UpdateRule** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="f11f2-118">В противном случае свойство **UpdateRule** имеет значение **CASCADE**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="f11f2-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="f11f2-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="f11f2-120">Если атрибут **DeleteRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **DeleteRule** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="f11f2-121">В противном случае свойство **DeleteRule** имеет значение **CASCADE**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="f11f2-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="f11f2-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="f11f2-123">Если атрибут **акцептрежектруле** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **акцептрежектруле** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="f11f2-124">В противном случае свойство **акцептрежектруле** имеет значение **None**.</span><span class="sxs-lookup"><span data-stu-id="f11f2-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="f11f2-125">В следующем примере показана схема, указывающая **ключ** и связи **keyref** между дочерним элементом **OrderNumber** элемента **Order** и дочерним элементом **ордерно** элемента **OrderDetail** . дерев.</span><span class="sxs-lookup"><span data-stu-id="f11f2-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="f11f2-126">В этом примере дочерний элемент **OrderNumber** элемента **OrderDetail** ссылается на дочерний элемент ключа **ордерно** элемента **Order** .</span><span class="sxs-lookup"><span data-stu-id="f11f2-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="f11f2-127">Процесс сопоставления схем на языке определения схем XML (XSD) создает следующий **набор данных** с двумя таблицами:</span><span class="sxs-lookup"><span data-stu-id="f11f2-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="f11f2-128">Кроме того, **набор данных** определяет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="f11f2-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="f11f2-129">Ограничение UNIQUE для таблицы **Order** .</span><span class="sxs-lookup"><span data-stu-id="f11f2-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="f11f2-130">Связь между таблицами **Order** и **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="f11f2-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="f11f2-131">**Вложенное** свойство имеет значение **false** , так как два элемента не вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="f11f2-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="f11f2-132">Ограничение внешнего ключа для таблицы **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="f11f2-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f11f2-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f11f2-133">See also</span></span>

- [<span data-ttu-id="f11f2-134">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="f11f2-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="f11f2-135">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f11f2-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="f11f2-136">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f11f2-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
