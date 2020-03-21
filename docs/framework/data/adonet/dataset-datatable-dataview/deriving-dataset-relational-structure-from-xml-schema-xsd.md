---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151173"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="f9161-102">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f9161-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="f9161-103">В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="f9161-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="f9161-104">Как правило, `complexType` для каждого элемента элемента схемы создается `DataSet`таблица в .</span><span class="sxs-lookup"><span data-stu-id="f9161-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="f9161-105">Структура таблицы задается определением сложного типа.</span><span class="sxs-lookup"><span data-stu-id="f9161-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="f9161-106">Таблицы создаются `DataSet` в элементах верхнего уровня в схеме.</span><span class="sxs-lookup"><span data-stu-id="f9161-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="f9161-107">Однако таблица создается только для `complexType` элемента `complexType` верхнего уровня, `complexType` когда элемент вложен внутри `complexType` другого элемента, `DataSet`и в этом случае вложенный элемент отображается в элементе `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="f9161-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="f9161-108">Для получения дополнительной информации о XSD, см. World Wide Web консорциум (W3C) [XML Схема Часть 0: Праймер Рекомендация](https://www.w3.org/TR/xmlschema-0/), [XML Схема Часть 1: Структуры Рекомендации](https://www.w3.org/TR/xmlschema-1/), и [XML Схема Часть 2: Рекомендация по типам данных](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="f9161-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="f9161-109">Следующий пример демонстрирует XML Schema, где `customers` находится `MyDataSet` элемент ребенка элемента, который является элементом **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="f9161-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="f9161-110">В предыдущем примере элемент `customers` является элементом сложного типа.</span><span class="sxs-lookup"><span data-stu-id="f9161-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="f9161-111">Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="f9161-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="f9161-112">Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9161-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9161-113">Если элемент `customers` имеет простой тип данных XML Schema, такой как **целый ряд,** таблица не генерируется.</span><span class="sxs-lookup"><span data-stu-id="f9161-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="f9161-114">Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="f9161-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="f9161-115">В следующей схеме XML элемент Schema имеет `InStateCustomers` два `OutOfStateCustomers` **элемента,** и .</span><span class="sxs-lookup"><span data-stu-id="f9161-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="f9161-116">Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="f9161-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="f9161-117">Таким образом, процесс отображения генерирует `DataSet`следующие две одинаковые таблицы в .</span><span class="sxs-lookup"><span data-stu-id="f9161-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="f9161-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f9161-118">In This Section</span></span>  
 [<span data-ttu-id="f9161-119">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="f9161-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="f9161-120">Описывает элементы XML Schema, используемые для `DataSet`создания уникальных и внешних ключевых ограничений в .</span><span class="sxs-lookup"><span data-stu-id="f9161-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="f9161-121">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f9161-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="f9161-122">Описывает элементы XML Schema, используемые для `DataSet`создания связей между столбиками таблицы в .</span><span class="sxs-lookup"><span data-stu-id="f9161-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="f9161-123">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="f9161-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="f9161-124">Описывает, как неявно создаются отношения при использовании элементов `DataSet`XML Schema для создания ограничений в .</span><span class="sxs-lookup"><span data-stu-id="f9161-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9161-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f9161-125">Related Sections</span></span>  
 [<span data-ttu-id="f9161-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="f9161-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="f9161-127">Описывает, как загружать и сохранять реляционную структуру и данные в `DataSet` данных XML.</span><span class="sxs-lookup"><span data-stu-id="f9161-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9161-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9161-128">See also</span></span>

- [<span data-ttu-id="f9161-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9161-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
