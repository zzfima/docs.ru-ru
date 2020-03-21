---
title: Создание отношений наборов данных из схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151134"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="58455-102">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="58455-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="58455-103">В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="58455-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="58455-104">Существует три способа представления отношения **DataSet** в схеме определения XML Schema (XSD):</span><span class="sxs-lookup"><span data-stu-id="58455-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="58455-105">Задайте вложенные сложные типы.</span><span class="sxs-lookup"><span data-stu-id="58455-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="58455-106">Используйте аннотацию **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="58455-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="58455-107">Укажите **xs:keyref** без **msdata:ConstraintOnly** аннотации.</span><span class="sxs-lookup"><span data-stu-id="58455-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="58455-108">Вложенные сложные типы</span><span class="sxs-lookup"><span data-stu-id="58455-108">Nested Complex Types</span></span>  
 <span data-ttu-id="58455-109">Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="58455-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="58455-110">Следующий фрагмент XML Schema показывает, что **OrderDetail** является элементом детского обеспечения элемента **Заказа.**</span><span class="sxs-lookup"><span data-stu-id="58455-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="58455-111">Процесс картирования XML Schema создает таблицы в **DataSet,** которые соответствуют вложенным типам сложных в схеме.</span><span class="sxs-lookup"><span data-stu-id="58455-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="58455-112">Он также создает дополнительные столбцы, которые используются в качестве родительских**-** столбцов для генерируемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="58455-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="58455-113">Обратите внимание,**-** что в этих родительских столбцах родительского элемента указаны отношения, что не соответствует указанию основных ограничений ключа/иностранных ключей.</span><span class="sxs-lookup"><span data-stu-id="58455-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="58455-114">Заметка msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="58455-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="58455-115">Аннотация **msdata:Relationship** позволяет явно указать отношения между родительскими и детскими отношениями между элементами в схеме, которые не вложены.</span><span class="sxs-lookup"><span data-stu-id="58455-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="58455-116">В следующем примере показана структура элемента **«Связь».**</span><span class="sxs-lookup"><span data-stu-id="58455-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="58455-117">Атрибуты **аннотации msdata:Relationship** идентифицируют элементы, участвующие в отношениях между родителем и ребенком, а также элементы и атрибуты родительского ключа **и** **детские** элементы, участвующие в отношениях.</span><span class="sxs-lookup"><span data-stu-id="58455-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="58455-118">Процесс картирования использует эту информацию для создания таблиц в **DataSet** и создания основных ключевых /иностранных ключевых отношений между этими таблицами.</span><span class="sxs-lookup"><span data-stu-id="58455-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="58455-119">Например, следующий фрагмент схемы определяет элементы **Order** и **OrderDetail** на одном уровне (не вложенные).</span><span class="sxs-lookup"><span data-stu-id="58455-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="58455-120">Схема определяет аннотацию **msdata:Relationship,** которая определяет отношения между родителем и ребенком между этими двумя элементами.</span><span class="sxs-lookup"><span data-stu-id="58455-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="58455-121">В этом случае явное отношение должно быть определено с помощью аннотации **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="58455-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="58455-122">Процесс отображения использует элемент **«Отношения»** для создания отношений между столбцом **OrderNumber** в таблице **Заказа** и столбцом **OrderNo** в таблице **OrderDetail** в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="58455-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="58455-123">Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного/внешнего ключа в реляционных базах данных.</span><span class="sxs-lookup"><span data-stu-id="58455-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="58455-124">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="58455-124">In This Section</span></span>  
 [<span data-ttu-id="58455-125">Сопоставление неявных отношений между вложенными элементами схемы</span><span class="sxs-lookup"><span data-stu-id="58455-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="58455-126">Описывает ограничения и связи, которые неявно создаются в **DataSet,** когда вложенные элементы встречаются в XML Schema.</span><span class="sxs-lookup"><span data-stu-id="58455-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="58455-127">Сопоставление отношений, заданных для вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="58455-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="58455-128">Описывает, как четко установить отношения в **DataSet** для вложенных элементов в XML Schema.</span><span class="sxs-lookup"><span data-stu-id="58455-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="58455-129">Указание отношений между элементами без вложенности</span><span class="sxs-lookup"><span data-stu-id="58455-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="58455-130">Описывает, как создать отношения в **DataSet** между элементами XML Schema, которые не вложены.</span><span class="sxs-lookup"><span data-stu-id="58455-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="58455-131">См. также</span><span class="sxs-lookup"><span data-stu-id="58455-131">Related Sections</span></span>  
 [<span data-ttu-id="58455-132">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="58455-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="58455-133">Описывает реляционную структуру, или схему, **DataSet,** которая создается из схемы определения XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="58455-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="58455-134">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="58455-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="58455-135">Описывает элементы XML Schema, используемые для создания уникальных и внешних ключевых ограничений в **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="58455-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58455-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="58455-136">See also</span></span>

- [<span data-ttu-id="58455-137">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="58455-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
