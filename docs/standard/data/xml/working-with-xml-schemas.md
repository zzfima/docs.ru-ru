---
title: "Работа с XML-схемами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a><span data-ttu-id="0a26c-102">Работа с XML-схемами</span><span class="sxs-lookup"><span data-stu-id="0a26c-102">Working with XML Schemas</span></span>
<span data-ttu-id="0a26c-103">Чтобы определить структуру XML-документа, связи его элементов, типы данных, ограничения на содержимое, используется определение типа документа (DTD) или схема XSD.</span><span class="sxs-lookup"><span data-stu-id="0a26c-103">To define the structure of an XML document, as well as its element relationships, data types, and content constraints, you use a document type definition (DTD) or XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="0a26c-104">XML-документ имеет правильный формат, если он соответствует всем синтаксическим требованиям Рекомендации консорциума W3C по языку XML 1.0. Однако документ считается допустимым только в том случае, если он одновременно имеет правильный формат и соответствует ограничениям, заданным определением DTD или схемой.</span><span class="sxs-lookup"><span data-stu-id="0a26c-104">Although an XML document is considered to be well-formed if it meets all the syntactical requirements defined by the World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0 Recommendation, it is not considered valid unless it is both well-formed and conforms to the constraints defined by its DTD or schema.</span></span> <span data-ttu-id="0a26c-105">Следовательно, хотя все допустимые XML-документы имеют правильный формат, не все XML-документы правильного формата, являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="0a26c-105">Therefore, although all valid XML documents are well-formed, not all well-formed XML documents are valid.</span></span>  
  
 <span data-ttu-id="0a26c-106">Дополнительные сведения о XML см. в разделе [рекомендация W3C XML 1.0](http://go.microsoft.com/fwlink/?linkid=7269).</span><span class="sxs-lookup"><span data-stu-id="0a26c-106">For more information about XML, see the [W3C XML 1.0 Recommendation](http://go.microsoft.com/fwlink/?linkid=7269).</span></span> <span data-ttu-id="0a26c-107">Дополнительные сведения о XML-схеме см. в разделе [W3C XML Schema Part 1: структурные рекомендации](http://go.microsoft.com/fwlink/?linkid=48881) и [W3C XML Schema Part 2: рекомендации по типам данных](http://go.microsoft.com/fwlink/?linkid=17392) рекомендации.</span><span class="sxs-lookup"><span data-stu-id="0a26c-107">For more information about XML Schema, see the [W3C XML Schema Part 1: Structures Recommendation](http://go.microsoft.com/fwlink/?linkid=48881) and the [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a26c-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="0a26c-108">In This Section</span></span>  
 [<span data-ttu-id="0a26c-109">Модель объектов схемы XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="0a26c-109">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="0a26c-110">Обсуждается модель SOM в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, предоставляющем набор классов, который позволяет считывать схему XSD из файла или создавать ее в памяти программным образом.</span><span class="sxs-lookup"><span data-stu-id="0a26c-110">Discusses the Schema Object Model (SOM) in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that provides a set of classes that allows you to read a Schema definition language (XSD) schema from a file or programmatically create a schema in-memory.</span></span>  
  
 [<span data-ttu-id="0a26c-111">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="0a26c-111">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 <span data-ttu-id="0a26c-112">Обсуждается класс <xref:System.Xml.Schema.XmlSchemaSet>, представляющий собой кэш, где могут храниться и проверяться схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="0a26c-112">Discusses the <xref:System.Xml.Schema.XmlSchemaSet> class that is a cache where XSD schemas can be stored and validated.</span></span>  
  
 [<span data-ttu-id="0a26c-113">Принудительная проверка с помощью XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="0a26c-113">XmlSchemaValidator Push-Based Validation</span></span>](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 <span data-ttu-id="0a26c-114">Обсуждается класс <xref:System.Xml.Schema.XmlSchemaValidator>, предоставляющий эффективный, высокопроизводительный механизм проверки XML-данных по схемам XSD в принудительном порядке.</span><span class="sxs-lookup"><span data-stu-id="0a26c-114">Discusses the <xref:System.Xml.Schema.XmlSchemaValidator> class that provides an efficient, high-performance mechanism to validate XML data against XSD schemas in a push-based manner.</span></span>  
  
 [<span data-ttu-id="0a26c-115">Определение схемы XML</span><span class="sxs-lookup"><span data-stu-id="0a26c-115">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 <span data-ttu-id="0a26c-116">Обсуждается применение класса <xref:System.Xml.Schema.XmlSchemaInference> для выведения схемы XSD из структуры XML-документа.</span><span class="sxs-lookup"><span data-stu-id="0a26c-116">Discusses how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XSD schema from the structure of an XML document.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a26c-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0a26c-117">Reference</span></span>  
 <span data-ttu-id="0a26c-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0a26c-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a26c-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0a26c-119">Related Sections</span></span>  
 [<span data-ttu-id="0a26c-120">Проверка XML-документа в DOM</span><span class="sxs-lookup"><span data-stu-id="0a26c-120">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 <span data-ttu-id="0a26c-121">Обсуждается проверка XML в модели DOM.</span><span class="sxs-lookup"><span data-stu-id="0a26c-121">Discusses how to validate the XML in the Document Object Model (DOM).</span></span> <span data-ttu-id="0a26c-122">XML можно проверять по мере загрузки в DOM, или проверять ранее не проверенный XML-документ в модели DOM.</span><span class="sxs-lookup"><span data-stu-id="0a26c-122">You can validate the XML as it is loaded into the DOM, or validate a previously unvalidated XML document in the DOM.</span></span>  
  
 [<span data-ttu-id="0a26c-123">Проверка схемы с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="0a26c-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="0a26c-124">Обсуждается проверка XML-документа, по которому производится перемещение и изменение с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="0a26c-124">Discusses how to validate XML being navigated and edited using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
