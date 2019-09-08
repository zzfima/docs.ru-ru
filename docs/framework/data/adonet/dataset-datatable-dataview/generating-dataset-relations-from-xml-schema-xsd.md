---
title: Создание отношений наборов данных из схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784648"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="56aa3-102">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="56aa3-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="56aa3-103">В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="56aa3-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="56aa3-104">Существует три способа представления связи **набора данных** в схеме языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="56aa3-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="56aa3-105">Задайте вложенные сложные типы.</span><span class="sxs-lookup"><span data-stu-id="56aa3-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="56aa3-106">Используйте аннотацию **msdata: relationship** .</span><span class="sxs-lookup"><span data-stu-id="56aa3-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="56aa3-107">Укажите **xs: keyref** без аннотации **msdata: констраинтонли** .</span><span class="sxs-lookup"><span data-stu-id="56aa3-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="56aa3-108">Вложенные сложные типы</span><span class="sxs-lookup"><span data-stu-id="56aa3-108">Nested Complex Types</span></span>  
 <span data-ttu-id="56aa3-109">Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="56aa3-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="56aa3-110">Следующий фрагмент схемы XML показывает, что элемент **OrderDetail** является дочерним элементом элемента **Order** .</span><span class="sxs-lookup"><span data-stu-id="56aa3-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="56aa3-111">Процесс сопоставления схем XML создает таблицы в **наборе данных** , соответствующие вложенным сложным типам в схеме.</span><span class="sxs-lookup"><span data-stu-id="56aa3-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="56aa3-112">Он также создает дополнительные столбцы, которые используются в качестве **-** родительских дочерних столбцов для создаваемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="56aa3-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="56aa3-113">Обратите внимание, **-** что эти родительские дочерние столбцы задают связи, которые не совпадают с указанием ограничений первичного и внешнего ключей.</span><span class="sxs-lookup"><span data-stu-id="56aa3-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="56aa3-114">Заметка msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="56aa3-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="56aa3-115">Аннотация **msdata: relationship** позволяет явно указать связи типа «родители-потомки» между элементами схемы, которые не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="56aa3-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="56aa3-116">В следующем примере показана структура элемента **Relationship** .</span><span class="sxs-lookup"><span data-stu-id="56aa3-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="56aa3-117">Атрибуты заметки **msdata: relationship** указывают элементы, участвующие в связи типа «родители-потомки», а также элементы и атрибуты **родительскими** и **чилдкэй** , участвующие в связи.</span><span class="sxs-lookup"><span data-stu-id="56aa3-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="56aa3-118">Процесс сопоставления использует эти сведения для создания таблиц в **наборе данных** и для создания связи первичного и внешнего ключей между этими таблицами.</span><span class="sxs-lookup"><span data-stu-id="56aa3-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="56aa3-119">Например, в следующем фрагменте схемы элементы **Order** и **OrderDetail** указываются на одном и том же уровне (не вложенном).</span><span class="sxs-lookup"><span data-stu-id="56aa3-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="56aa3-120">Схема задает аннотацию **msdata: relationship** , которая указывает связь типа «родители-потомки» между этими двумя элементами.</span><span class="sxs-lookup"><span data-stu-id="56aa3-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="56aa3-121">В этом случае необходимо указать явную связь с помощью аннотации **msdata: relationship** .</span><span class="sxs-lookup"><span data-stu-id="56aa3-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="56aa3-122">В процессе сопоставления используется элемент **Relationship** для создания связи типа «родители-потомки» между столбцом **OrderNumber** в таблице **Order** и столбцом **Ордерно** в таблице **OrderDetail** в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="56aa3-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="56aa3-123">Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного/внешнего ключа в реляционных базах данных.</span><span class="sxs-lookup"><span data-stu-id="56aa3-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="56aa3-124">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="56aa3-124">In This Section</span></span>  
 [<span data-ttu-id="56aa3-125">Сопоставление неявных отношений между вложенными элементами схемы</span><span class="sxs-lookup"><span data-stu-id="56aa3-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="56aa3-126">Описывает ограничения и связи, которые неявно создаются в **наборе данных** при обнаружении вложенных элементов в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="56aa3-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="56aa3-127">Сопоставление отношений, заданных для вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="56aa3-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="56aa3-128">Описывает, как явно задать связи в **наборе данных** для вложенных элементов в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="56aa3-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="56aa3-129">Указание отношений между элементами без вложенности</span><span class="sxs-lookup"><span data-stu-id="56aa3-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="56aa3-130">Описывает создание связей в **наборе данных** между невложенными ЭЛЕМЕНТАМИ XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="56aa3-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="56aa3-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="56aa3-131">Related Sections</span></span>  
 [<span data-ttu-id="56aa3-132">Наследование реляционной структуры DataSet от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="56aa3-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="56aa3-133">Описывает реляционную структуру или схему **набора данных** , созданного из схемы языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="56aa3-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="56aa3-134">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="56aa3-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="56aa3-135">Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE и FOREIGN KEY в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="56aa3-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56aa3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="56aa3-136">See also</span></span>

- [<span data-ttu-id="56aa3-137">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="56aa3-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
