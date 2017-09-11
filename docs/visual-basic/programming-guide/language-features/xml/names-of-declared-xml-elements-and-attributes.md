---
title: "Имена объявленных элементов и атрибутов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2c0bb2350f50138d00e202e2e887a2202d21942f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="9340e-102">Имена объявляемых элементов и атрибутов XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9340e-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="9340e-103">В этом разделе приведены [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] соглашения об именах элементов и атрибутов в XML-литералах XML.</span><span class="sxs-lookup"><span data-stu-id="9340e-103">This topic provides [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="9340e-104">В литерале XML можно указать локальное имя или полное имя.</span><span class="sxs-lookup"><span data-stu-id="9340e-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="9340e-105">Полное имя состоит из префикса пространства имен XML, двоеточия и локального имени.</span><span class="sxs-lookup"><span data-stu-id="9340e-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="9340e-106">Дополнительные сведения о префиксы пространства имен XML, в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="9340e-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9340e-107">Правила</span><span class="sxs-lookup"><span data-stu-id="9340e-107">Rules</span></span>  
 <span data-ttu-id="9340e-108">Локальное имя элемента или атрибута в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должны соответствовать следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="9340e-108">A local name of an element or attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="9340e-109">Его можно начать с пространством имен.</span><span class="sxs-lookup"><span data-stu-id="9340e-109">It can begin with a namespace.</span></span> <span data-ttu-id="9340e-110">Оно должно начинаться с алфавитного символа или знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="9340e-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="9340e-111">Он должен содержать только буквы, десятичные цифры, подчеркивания, точки (.) и дефисы (-).</span><span class="sxs-lookup"><span data-stu-id="9340e-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="9340e-112">Оно не должно быть более 1024 символов.</span><span class="sxs-lookup"><span data-stu-id="9340e-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="9340e-113">Двоеточия, отображаемые в именах указывает разделение пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9340e-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="9340e-114">Таким образом можно использовать двоеточия только для указания пространства имен XML для определенного имени.</span><span class="sxs-lookup"><span data-stu-id="9340e-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="9340e-115">Кроме того следует придерживаться следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="9340e-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="9340e-116">Спецификации XML 1.0 резервируются все имена, начинающиеся со строки «xml», любое изменение регистра символов.</span><span class="sxs-lookup"><span data-stu-id="9340e-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="9340e-117">Таким образом не используйте эти имена для элемента и имен атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9340e-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="9340e-118">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="9340e-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="9340e-119">На практике имя должно быть как можно более короткими, при этом четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="9340e-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="9340e-120">Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.</span><span class="sxs-lookup"><span data-stu-id="9340e-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="9340e-121">Однако имя не должно быть настолько коротким, что оно не адекватно описывает элемент или как код использует.</span><span class="sxs-lookup"><span data-stu-id="9340e-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="9340e-122">Это важно для удобства чтения кода.</span><span class="sxs-lookup"><span data-stu-id="9340e-122">This is important for the readability of your code.</span></span> <span data-ttu-id="9340e-123">Если кто-то еще пытается разобраться, или вы сами вернетесь к нему длительное время после написания, подходящие имена элементов могут сэкономить время.</span><span class="sxs-lookup"><span data-stu-id="9340e-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="9340e-124">Учет регистра в именах</span><span class="sxs-lookup"><span data-stu-id="9340e-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="9340e-125">Имена элементов XML учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9340e-125">XML element names are case sensitive.</span></span> <span data-ttu-id="9340e-126">Это означает, что при [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор сравнивает два имени, отличающихся только регистром буквенных, воспринимает их как разные имена.</span><span class="sxs-lookup"><span data-stu-id="9340e-126">This means that when the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="9340e-127">Например, он интерпретирует `ABC` и `abc` как ссылки на различные элементы.</span><span class="sxs-lookup"><span data-stu-id="9340e-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="9340e-128">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="9340e-128">XML Namespaces</span></span>  
 <span data-ttu-id="9340e-129">При создании литерала XML-элемента, можно указать префикс пространства имен XML для имени элемента.</span><span class="sxs-lookup"><span data-stu-id="9340e-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="9340e-130">Дополнительные сведения см. в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="9340e-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9340e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9340e-131">See Also</span></span>  
 <span data-ttu-id="9340e-132">[Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9340e-132">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="9340e-133"> [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span><span class="sxs-lookup"><span data-stu-id="9340e-133"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span></span>
