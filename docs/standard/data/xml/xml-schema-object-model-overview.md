---
title: "Общие сведения об модели объектов XML-схемы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e18a3151228ea7edb5a8380f6ed707ee88d369e5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="xml-schema-object-model-overview"></a><span data-ttu-id="4e2bf-102">Общие сведения об модели объектов XML-схемы</span><span class="sxs-lookup"><span data-stu-id="4e2bf-102">XML Schema Object Model Overview</span></span>
<span data-ttu-id="4e2bf-103">Модель SOM в Microsoft .NET Framework является богатым по возможностям API, позволяющим создавать, изменять и проверять схемы программным путем.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-103">The Schema Object Model (SOM) in the Microsoft .NET Framework is a rich API that allows you to create, edit, and validate schemas programmatically.</span></span> <span data-ttu-id="4e2bf-104">Модель SOM работает в документах схемы XML так же, как модель DOM работает в XML-документах.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-104">The SOM operates on XML schema documents similarly to the way the Document Object Model (DOM) operates on XML documents.</span></span> <span data-ttu-id="4e2bf-105">Документы схемы XML - это допустимые XML-файлы, которые после загрузки в память делают осмысленными утверждения о структуре и правильности других XML-документов, соответствующих этой схеме.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-105">XML schema documents are valid XML files that, once loaded into the SOM, convey meaning about the structure and validity of other XML documents which conform to the schema.</span></span>  
  
 <span data-ttu-id="4e2bf-106">Схема представляет собой XML-документ, который определяет класс XML-документов, указывая структуру или модель XML-документа для конкретной схемы.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-106">A schema is an XML document that defines a class of XML documents by specifying the structure or model of XML documents for a particular schema.</span></span> <span data-ttu-id="4e2bf-107">В схеме определяются ограничения на содержимое XML-документов и описывается словарь (правила или грамматика), которому должны следовать совместимые с ней XML-документы, чтобы считаться допустимыми для этой конкретной схемы.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-107">A schema identifies the constraints on the content of the XML documents, and describes the vocabulary (rules or grammar) that compliant XML documents must follow in order to be considered schema-valid with that particular schema.</span></span> <span data-ttu-id="4e2bf-108">Проверка XML-документа - это процесс, обеспечивающий соответствие документа заданной схемой грамматике.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-108">Validation of an XML document is the process that ensures that the document conforms to the grammar specified by the schema.</span></span>  
  
 <span data-ttu-id="4e2bf-109">Ниже представлены способы, с помощью которых API модели SOM в платформе .NET Framework позволяет создавать, изменять и проверять схемы.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-109">The following are ways the SOM API in the .NET Framework enables you to create, edit, and validate schemas.</span></span>  
  
-   <span data-ttu-id="4e2bf-110">Загрузка допустимых схем из файлов и сохранение их в файл.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-110">Load and save valid schemas to and from files.</span></span>  
  
-   <span data-ttu-id="4e2bf-111">Создание в памяти схем, использующих классы со строгой типизацией.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-111">Create in-memory schemas using strongly typed classes.</span></span>  
  
-   <span data-ttu-id="4e2bf-112">Взаимодействие с классом <xref:System.Xml.Schema.XmlSchemaSet> для кэширования, компиляции и получения схем.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-112">Interact with the <xref:System.Xml.Schema.XmlSchemaSet> class to cache, compile, and retrieve schemas.</span></span>  
  
-   <span data-ttu-id="4e2bf-113">Взаимодействие с методом <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader> для проверки соответствия экземпляров XML-документов схемам.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-113">Interact with the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to validate XML instance documents against schemas.</span></span>  
  
-   <span data-ttu-id="4e2bf-114">Построение редакторов для создания и обслуживания схем.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-114">Build editors for creating and maintaining schemas.</span></span>  
  
-   <span data-ttu-id="4e2bf-115">Динамическое изменение схемы, которую можно скомпилировать и сохранить для использования в проверке экземпляров XML-документов.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-115">Dynamically edit a schema that can be complied and saved for use in the validation of XML instance documents.</span></span>  
  
## <a name="the-schema-object-model"></a><span data-ttu-id="4e2bf-116">Модель SOM</span><span class="sxs-lookup"><span data-stu-id="4e2bf-116">The Schema Object Model</span></span>  
 <span data-ttu-id="4e2bf-117">Модель SOM состоит из широкого набора классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, соответствующих элементам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-117">The SOM consists of an extensive set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace corresponding to the elements in an XML schema.</span></span> <span data-ttu-id="4e2bf-118">Например, элемент `<xsd:schema>...</xsd:schema>` сопоставляется с классом <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType>, а все данные, содержащиеся в элементе `<xsd:schema/>`, можно представить с помощью класса <xref:System.Xml.Schema.XmlSchema>.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-118">For example, the `<xsd:schema>...</xsd:schema>` element maps to the <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> class, and all the information that can be contained within an `<xsd:schema/>` element can be represented using the <xref:System.Xml.Schema.XmlSchema> class.</span></span> <span data-ttu-id="4e2bf-119">Точно так же элементы `<xsd:element>...</xsd:element>` и `<xsd:attribute>...</xsd:attribute>` сопоставляются с классами <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> и <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> соответственно.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-119">Similarly, the `<xsd:element>...</xsd:element>` and `<xsd:attribute>...</xsd:attribute>` elements map to the <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> and <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> classes respectively.</span></span> <span data-ttu-id="4e2bf-120">Это сопоставление выполняется для всех элементов схемы XML, создающих модели XML SOM в пространстве имен <xref:System.Xml.Schema>, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-120">This mapping continues for all the elements of an XML schema creating an XML schema object model in the <xref:System.Xml.Schema> namespace illustrated in the diagram that follows.</span></span>  
  
 <span data-ttu-id="4e2bf-121">![Объектная модель System.Xml.Schema](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span><span class="sxs-lookup"><span data-stu-id="4e2bf-121">![System.Xml.Schema Object Model](../../../../docs/standard/data/xml/media/xmlschemaobjmodeloverview.gif "XMLSchemaObjModelOverview")</span></span>  
  
 <span data-ttu-id="4e2bf-122">Дополнительные сведения о каждом классе в пространстве имен <xref:System.Xml.Schema> см. в справочной документации для пространства имен <xref:System.Xml.Schema> в библиотеке классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e2bf-122">For more information about each class in the <xref:System.Xml.Schema> namespace, see the <xref:System.Xml.Schema> namespace reference documentation in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2bf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4e2bf-123">See Also</span></span>  
 [<span data-ttu-id="4e2bf-124">Чтение и запись XML-схем</span><span class="sxs-lookup"><span data-stu-id="4e2bf-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="4e2bf-125">Построение XML-схем</span><span class="sxs-lookup"><span data-stu-id="4e2bf-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="4e2bf-126">Обход XML-схем</span><span class="sxs-lookup"><span data-stu-id="4e2bf-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="4e2bf-127">Изменение XML-схем</span><span class="sxs-lookup"><span data-stu-id="4e2bf-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="4e2bf-128">Включение или импорт XML-схем</span><span class="sxs-lookup"><span data-stu-id="4e2bf-128">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="4e2bf-129">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="4e2bf-129">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="4e2bf-130">Набор сведений для постсхемной компиляции</span><span class="sxs-lookup"><span data-stu-id="4e2bf-130">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
