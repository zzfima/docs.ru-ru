---
title: "Наследование реляционной структуры набора данных от схемы XML (XSD)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3fcedf488a038f379bae26fd7da0f4bf027b2e55
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="faf45-102">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="faf45-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="faf45-103">В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="faf45-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="faf45-104">Как правило, для каждого `complexType` дочерний элемент элемента схемы, создается таблица, в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="faf45-105">Структура таблицы задается определением сложного типа.</span><span class="sxs-lookup"><span data-stu-id="faf45-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="faf45-106">Таблицы создаются в `DataSet` для элементов верхнего уровня в схеме.</span><span class="sxs-lookup"><span data-stu-id="faf45-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="faf45-107">Однако таблица создается только для верхнего уровня `complexType` элемент при `complexType` элемент вложен в другой `complexType` случае вложенный элемент, в котором `complexType` элемент сопоставляется `DataTable` в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="faf45-108">Дополнительные сведения о языке XSD см. в разделе World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, XML Schema Part 1: структурные рекомендации и XML Schema Part 2: рекомендации по типам данных, расположенном в [http:// www.w3.org/](http://www.w3.org/TR/).</span><span class="sxs-lookup"><span data-stu-id="faf45-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="faf45-109">Ниже приведен пример XML-схемы где `customers` является дочерним элементом элемента `MyDataSet` элемент, являющийся **DataSet** элемента.</span><span class="sxs-lookup"><span data-stu-id="faf45-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="faf45-110">В предыдущем примере элемент `customers` является элементом сложного типа.</span><span class="sxs-lookup"><span data-stu-id="faf45-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="faf45-111">Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="faf45-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="faf45-112">Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="faf45-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faf45-113">Если элемент `customers` — простого типа данных XML-схемы, таких как **целое**, то таблица не создается.</span><span class="sxs-lookup"><span data-stu-id="faf45-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="faf45-114">Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="faf45-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="faf45-115">В следующей схеме XML **схемы** элемент имеет два дочерних элемента: `InStateCustomers` и `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="faf45-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="faf45-116">Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="faf45-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="faf45-117">Таким образом, процесс сопоставления создает две следующие одинаковые таблицы в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="faf45-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="faf45-118">In This Section</span></span>  
 [<span data-ttu-id="faf45-119">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="faf45-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="faf45-120">Описывает элементы схемы XML, используемые для создания ограничений уникального и внешнего ключа в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="faf45-121">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="faf45-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="faf45-122">Описывает элементы схемы XML, используемых для создания связей между столбцами таблиц в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="faf45-123">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="faf45-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="faf45-124">Описывает, каким образом неявного создания связей при использовании элементов схемы XML для создания ограничений в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="faf45-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="faf45-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="faf45-125">Related Sections</span></span>  
 [<span data-ttu-id="faf45-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="faf45-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="faf45-127">Описывает, как для загрузки и сохранения реляционной структуры и данных в `DataSet` как XML-данных.</span><span class="sxs-lookup"><span data-stu-id="faf45-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf45-128">См. также</span><span class="sxs-lookup"><span data-stu-id="faf45-128">See Also</span></span>  
 [<span data-ttu-id="faf45-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="faf45-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
