---
title: Директивы таблицы стилей, встроенные в документ
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08bd33aab6cbeeeb9060f3de3565a05896c6ba7f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001351"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="199cd-102">Директивы таблицы стилей, встроенные в документ</span><span class="sxs-lookup"><span data-stu-id="199cd-102">Style Sheet Directives Embedded in a Document</span></span>

<span data-ttu-id="199cd-103">Иногда существующий XML содержит директивы таблицы стилей `<?xml:stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="199cd-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="199cd-104">Обозреватель Microsoft Internet Explorer обрабатывает этот синтаксис как альтернативу `<?xml-stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="199cd-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="199cd-105">Если данные XML содержат директиву `<?xml:stylesheet?>`, как показано в следующем примере, при попытке загрузить эти данные в модель XML DOM будет сформировано исключение.</span><span class="sxs-lookup"><span data-stu-id="199cd-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

<span data-ttu-id="199cd-106">Это происходит потому, что конструкция `<?xml:stylesheet?>` с точки зрения модели DOM представляет собой недопустимую инструкцию **ProcessingInstruction**.</span><span class="sxs-lookup"><span data-stu-id="199cd-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="199cd-107">Согласно спецификации пространства имен в XML, инструкции **ProcessingInstruction** могут быть только именами, не содержащими двоеточий (NCNames), в противоположность полным именам (QNames).</span><span class="sxs-lookup"><span data-stu-id="199cd-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>

<span data-ttu-id="199cd-108">Согласно разделу 6 спецификации пространств имен в XML наличие методов **Load** и **LoadXml** обеспечивает выполнение в документе следующих условий:</span><span class="sxs-lookup"><span data-stu-id="199cd-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>

- <span data-ttu-id="199cd-109">Все типы элементов и имена атрибутов содержат одно двоеточие или не содержат ни одного.</span><span class="sxs-lookup"><span data-stu-id="199cd-109">All element types and attribute names contain either zero or one colon.</span></span>

- <span data-ttu-id="199cd-110">Имена сущностей, цели инструкции ProcessingInstruction и имена нотаций не могут содержать двоеточий.</span><span class="sxs-lookup"><span data-stu-id="199cd-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>

<span data-ttu-id="199cd-111">Поскольку конструкция `<?xml:stylesheet?>` содержит двоеточие, это является нарушением второго правила.</span><span class="sxs-lookup"><span data-stu-id="199cd-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>

<span data-ttu-id="199cd-112">Согласно рекомендации консорциума W3C [Связь таблиц стилей с XML-документами версии 1.0](https://www.w3.org/TR/xml-stylesheet/), инструкция по обработке, связывающая таблицу стилей XSLT с XML-документом, выглядит следующим образом: `<?xml-stylesheet?>`, то есть двоеточие заменено на тире.</span><span class="sxs-lookup"><span data-stu-id="199cd-112">According to the World Wide Web Consortium (W3C) [Associating Style Sheets with XML documents Version 1.0 Recommendation](https://www.w3.org/TR/xml-stylesheet/),  the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>

## <a name="see-also"></a><span data-ttu-id="199cd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="199cd-113">See Also</span></span>

[<span data-ttu-id="199cd-114">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="199cd-114">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)  