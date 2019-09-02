---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 611322065a4df53d1a3149ef4e1ca5592f149081
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203437"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="640ef-102">Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="640ef-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="640ef-103">Элемент **keyref** позволяет устанавливать связи между элементами в документе.</span><span class="sxs-lookup"><span data-stu-id="640ef-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="640ef-104">Это похоже на связь по внешнему ключу в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="640ef-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="640ef-105">Если схема указывает элемент **keyref** , элемент преобразуется в процессе сопоставления схемы в соответствующее ограничение FOREIGN KEY для столбцов в таблицах <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="640ef-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="640ef-106">По умолчанию элемент **keyref** также создает отношение со свойствами **паренттабле**, **ChildTable**, **парентколумн**и **чилдколумн** , указанными для отношения.</span><span class="sxs-lookup"><span data-stu-id="640ef-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="640ef-107">В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **keyref** .</span><span class="sxs-lookup"><span data-stu-id="640ef-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="640ef-108">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="640ef-108">Attribute name</span></span>|<span data-ttu-id="640ef-109">Описание</span><span class="sxs-lookup"><span data-stu-id="640ef-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="640ef-110">**msdata: Констраинтонли**</span><span class="sxs-lookup"><span data-stu-id="640ef-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="640ef-111">Если для элемента **keyref** схемы задано **значение констраинтонли = "true"** , то создается ограничение, но связь не создается.</span><span class="sxs-lookup"><span data-stu-id="640ef-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="640ef-112">Если этот атрибут не задан (или имеет значение **false**), в **наборе данных**создается и ограничение, и отношение.</span><span class="sxs-lookup"><span data-stu-id="640ef-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="640ef-113">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="640ef-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="640ef-114">Если указан атрибут **ConstraintName** , его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="640ef-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="640ef-115">В противном случае атрибут **Name** элемента **keyref** в схеме предоставляет имя ограничения в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="640ef-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="640ef-116">**msdata: UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="640ef-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="640ef-117">Если атрибут **UpdateRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **UpdateRule** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="640ef-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="640ef-118">В противном случае свойство **UpdateRule** имеет значение **CASCADE**.</span><span class="sxs-lookup"><span data-stu-id="640ef-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="640ef-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="640ef-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="640ef-120">Если атрибут **DeleteRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **DeleteRule** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="640ef-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="640ef-121">В противном случае свойство **DeleteRule** имеет значение **CASCADE**.</span><span class="sxs-lookup"><span data-stu-id="640ef-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="640ef-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="640ef-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="640ef-123">Если атрибут **акцептрежектруле** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **акцептрежектруле** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="640ef-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="640ef-124">В противном случае свойство **акцептрежектруле** имеет значение **None**.</span><span class="sxs-lookup"><span data-stu-id="640ef-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="640ef-125">В следующем примере показана схема, указывающая **ключ** и связи **keyref** между дочерним элементом **OrderNumber** элемента **Order** и дочерним элементом **ордерно** элемента **OrderDetail** . дерев.</span><span class="sxs-lookup"><span data-stu-id="640ef-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="640ef-126">В этом примере дочерний элемент **OrderNumber** элемента **OrderDetail** ссылается на дочерний элемент ключа **ордерно** элемента **Order** .</span><span class="sxs-lookup"><span data-stu-id="640ef-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="640ef-127">Процесс сопоставления схем на языке определения схем XML (XSD) создает следующий **набор данных** с двумя таблицами:</span><span class="sxs-lookup"><span data-stu-id="640ef-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="640ef-128">Кроме того, **набор данных** определяет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="640ef-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="640ef-129">Ограничение UNIQUE для таблицы **Order** .</span><span class="sxs-lookup"><span data-stu-id="640ef-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="640ef-130">Связь между таблицами **Order** и **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="640ef-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="640ef-131">**Вложенное** свойство имеет значение **false** , так как два элемента не вложены в схему.</span><span class="sxs-lookup"><span data-stu-id="640ef-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="640ef-132">Ограничение внешнего ключа для таблицы **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="640ef-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="640ef-133">См. также</span><span class="sxs-lookup"><span data-stu-id="640ef-133">See also</span></span>

- [<span data-ttu-id="640ef-134">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="640ef-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="640ef-135">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="640ef-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="640ef-136">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="640ef-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
