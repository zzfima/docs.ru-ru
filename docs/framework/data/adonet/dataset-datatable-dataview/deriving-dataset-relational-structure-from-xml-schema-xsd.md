---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 29b905c42f15cad4eb8521c4d702b56093982445
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203776"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="5fb80-102">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="5fb80-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="5fb80-103">В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="5fb80-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="5fb80-104">Как правило, для каждого `complexType` дочернего элемента в элементе Schema создается таблица `DataSet`в.</span><span class="sxs-lookup"><span data-stu-id="5fb80-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="5fb80-105">Структура таблицы задается определением сложного типа.</span><span class="sxs-lookup"><span data-stu-id="5fb80-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="5fb80-106">Таблицы создаются в `DataSet` для элементов верхнего уровня схемы.</span><span class="sxs-lookup"><span data-stu-id="5fb80-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="5fb80-107">Однако таблица создается только для элемента верхнего уровня `complexType` , `complexType` если элемент вложен в другой `complexType` элемент `DataSet`. в этом случае вложенный `complexType` элемент сопоставляется с элементом `DataTable` в.</span><span class="sxs-lookup"><span data-stu-id="5fb80-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="5fb80-108">Дополнительные сведения о XSD см. в разделе консорциум W3C (W3C) [XML-схема, часть 0. Рекомендации](https://www.w3.org/TR/xmlschema-0/) по[основам, схема XML, часть 1: Рекомендации](https://www.w3.org/TR/xmlschema-1/) по[структурам и схеме XML, часть 2: Рекомендация по типам данных](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="5fb80-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="5fb80-109">В следующем примере показана схема XML, `customers` где — это дочерний `MyDataSet` элемент элемента DataSet, который является элементом **набора данных** .</span><span class="sxs-lookup"><span data-stu-id="5fb80-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="5fb80-110">В предыдущем примере элемент `customers` является элементом сложного типа.</span><span class="sxs-lookup"><span data-stu-id="5fb80-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="5fb80-111">Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="5fb80-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="5fb80-112">Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="5fb80-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fb80-113">Если элемент `customers` имеет простой тип данных схемы XML, такой как **Integer**, таблица не создается.</span><span class="sxs-lookup"><span data-stu-id="5fb80-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="5fb80-114">Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="5fb80-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="5fb80-115">В следующей схеме XML элемент **Schema** имеет два дочерних элемента, `InStateCustomers` и. `OutOfStateCustomers`</span><span class="sxs-lookup"><span data-stu-id="5fb80-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="5fb80-116">Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="5fb80-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="5fb80-117">Таким образом, процесс сопоставления создает следующие две идентичные таблицы в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="5fb80-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="5fb80-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5fb80-118">In This Section</span></span>  
 [<span data-ttu-id="5fb80-119">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="5fb80-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="5fb80-120">Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE и FOREIGN KEY в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="5fb80-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="5fb80-121">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="5fb80-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="5fb80-122">Описывает элементы XML-схемы, `DataSet`используемые для создания связей между столбцами таблицы в.</span><span class="sxs-lookup"><span data-stu-id="5fb80-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="5fb80-123">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="5fb80-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="5fb80-124">Описывает, как неявным образом создаются связи при использовании элементов схемы XML для создания ограничений `DataSet`в.</span><span class="sxs-lookup"><span data-stu-id="5fb80-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5fb80-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5fb80-125">Related Sections</span></span>  
 [<span data-ttu-id="5fb80-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="5fb80-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="5fb80-127">Описывает загрузку и сохранение реляционной структуры и данных в `DataSet` виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="5fb80-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb80-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5fb80-128">See also</span></span>

- [<span data-ttu-id="5fb80-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fb80-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
