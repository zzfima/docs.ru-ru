---
title: "Директивы таблицы стилей, встроенные в документ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="e6a32-102">Директивы таблицы стилей, встроенные в документ</span><span class="sxs-lookup"><span data-stu-id="e6a32-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="e6a32-103">Иногда существующий XML содержит директивы таблицы стилей `<?xml:stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="e6a32-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="e6a32-104">Microsoft Internet Explorer в качестве альтернативы принимает это `<?xml-stylesheet?>` синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e6a32-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="e6a32-105">Если данные XML содержат директиву `<?xml:stylesheet?>`, как показано в следующем примере, при попытке загрузить эти данные в модель XML DOM будет сформировано исключение.</span><span class="sxs-lookup"><span data-stu-id="e6a32-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="e6a32-106">Это происходит потому, что `<?xml:stylesheet?>` представляет собой недопустимую **ProcessingInstruction** с моделью DOM.</span><span class="sxs-lookup"><span data-stu-id="e6a32-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="e6a32-107">Любой **ProcessingInstruction**, согласно спецификации пространства имен в XML, может быть только имена без двоеточий (NCNames), противоположность полным именам (QNames).</span><span class="sxs-lookup"><span data-stu-id="e6a32-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="e6a32-108">Согласно разделу 6 спецификации пространства имен в XML, эффект отсутствия **нагрузки** и **LoadXml** методы соответствует спецификации, находится в документе:</span><span class="sxs-lookup"><span data-stu-id="e6a32-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="e6a32-109">Все типы элементов и имена атрибутов содержат одно двоеточие или не содержат ни одного.</span><span class="sxs-lookup"><span data-stu-id="e6a32-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="e6a32-110">Имена сущностей, цели инструкции ProcessingInstruction и имена нотаций не могут содержать двоеточий.</span><span class="sxs-lookup"><span data-stu-id="e6a32-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="e6a32-111">Поскольку конструкция `<?xml:stylesheet?>` содержит двоеточие, это является нарушением второго правила.</span><span class="sxs-lookup"><span data-stu-id="e6a32-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="e6a32-112">Согласно рекомендации W3C «Связь таблиц стилей с XML-документами» версии 1.0, расположенной по адресу www.w3.org/TR/xml-stylesheet, инструкция по обработке, связывающая таблицу стилей XSLT с XML-документом, выглядит следующим образом: `<?xml-stylesheet?>`, то есть двоеточие заменено на тире.</span><span class="sxs-lookup"><span data-stu-id="e6a32-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a32-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e6a32-113">See Also</span></span>  
 [<span data-ttu-id="e6a32-114">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="e6a32-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
