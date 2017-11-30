---
title: "Компиляция схемы XmlSchemaCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="e6738-102">Компиляция схемы XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e6738-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="e6738-103">**XmlSchemaCollection** кэша или библиотеки, где хранятся и проверки схемы языка XSD определения XML-Data Reduced (XDR) и XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="e6738-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="e6738-104">**XmlSchemaCollection** повышает производительность за счет кэширования схем в памяти вместо обращения к ним из файла или URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e6738-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6738-105">Несмотря на то что **XmlSchemaCollection** класс хранит XDR-схемы и XML-схем, любые методы и свойства, которое принимает или возвращает **XmlSchema** объектов поддерживает только схемы XML.</span><span class="sxs-lookup"><span data-stu-id="e6738-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6738-106">Класс <xref:System.Xml.Schema.XmlSchemaCollection> устарел и заменен классом <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="e6738-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="e6738-107">Дополнительные сведения о <xref:System.Xml.Schema.XmlSchemaSet> см. класс, [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="e6738-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="e6738-108">Добавление схем в коллекцию</span><span class="sxs-lookup"><span data-stu-id="e6738-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="e6738-109">Схемы загружаются в коллекцию с помощью **добавить** метод **XmlSchemaCollection**, во время работы которого схема связывается с URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e6738-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="e6738-110">Для схем XML URI-код пространства имен обычно является целевым пространством имен для схемы.</span><span class="sxs-lookup"><span data-stu-id="e6738-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="e6738-111">Для схем XDR URI-код пространства имен будет задаваться во время добавления схемы в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e6738-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="e6738-112">Проверка наличия схемы в коллекции</span><span class="sxs-lookup"><span data-stu-id="e6738-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="e6738-113">Можно проверить, находится ли схема в коллекции с помощью **Contains** метод.</span><span class="sxs-lookup"><span data-stu-id="e6738-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="e6738-114">**Contains** метод принимает либо **XmlSchema** объекта (только для схем XML) или строка, представляющая пространство имен URI, связанное со схемой (для схем XML и XDR).</span><span class="sxs-lookup"><span data-stu-id="e6738-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="e6738-115">Получение схемы из коллекции</span><span class="sxs-lookup"><span data-stu-id="e6738-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="e6738-116">Можно получить схему из коллекции с помощью **элемент** свойство.</span><span class="sxs-lookup"><span data-stu-id="e6738-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="e6738-117">**Элемент** свойство принимает строку, представляющую пространство имен URI, связанное со схемой, обычно целевое пространство имен и возвращает **XmlSchema** объекта.</span><span class="sxs-lookup"><span data-stu-id="e6738-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="e6738-118">**Элемент** свойство применяется только к XML-схем.</span><span class="sxs-lookup"><span data-stu-id="e6738-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="e6738-119">Для схем XDR всегда возвращается ссылка NULL, поскольку для них нет доступной модели объектов.</span><span class="sxs-lookup"><span data-stu-id="e6738-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="e6738-120">Проверка XML-документов с помощью XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e6738-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="e6738-121">Можно проверить экземпляр XML-документа при помощи **XmlSchemaCollection** путем создания **XmlSchemaCollection** объекта, добавив схемы в коллекцию и задание **схемы**  свойство **XmlValidatingReader** Чтобы назначить созданную **XmlSchemaCollection** для **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="e6738-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="e6738-122">Повышенная производительность</span><span class="sxs-lookup"><span data-stu-id="e6738-122">Improved Performance</span></span>  
 <span data-ttu-id="e6738-123">Рекомендуется, если проверяются более одного документа по одной схеме, которая используется **XmlSchemaCollection** из-за счет кэширования схем в памяти, он обеспечивает более высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="e6738-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="e6738-124">В следующем примере кода создается **XmlSchemaCollection** , схемы добавляются в коллекцию и задается **схемы** свойство.</span><span class="sxs-lookup"><span data-stu-id="e6738-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6738-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e6738-125">See Also</span></span>  
 [<span data-ttu-id="e6738-126">Проверка XDR с помощью XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e6738-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="e6738-127">Проверка схемы (XSD) XML с помощью XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="e6738-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
