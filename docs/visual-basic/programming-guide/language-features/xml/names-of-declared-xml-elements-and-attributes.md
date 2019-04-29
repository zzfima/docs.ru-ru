---
title: Имена объявляемых элементов и атрибутов XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761706"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="b4d7d-102">Имена объявляемых элементов и атрибутов XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4d7d-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="b4d7d-103">В этом разделе приведены рекомендации Visual Basic по именованию XML-элементов и атрибутов в XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="b4d7d-104">В литерале XML можно указать локальное имя или полное имя.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="b4d7d-105">Полное имя состоит из префикса пространства имен XML, двоеточия и локального имени.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="b4d7d-106">Дополнительные сведения о префиксы пространства имен XML, см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b4d7d-107">Правила</span><span class="sxs-lookup"><span data-stu-id="b4d7d-107">Rules</span></span>  
 <span data-ttu-id="b4d7d-108">Локальное имя элемента или атрибута в Visual Basic необходимо соблюдать следующие правила.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="b4d7d-109">Она может начинаться с пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-109">It can begin with a namespace.</span></span> <span data-ttu-id="b4d7d-110">Он должен начинаться с алфавитного символа или символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="b4d7d-111">Он должен содержать только буквы, десятичные цифры, символы подчеркивания, точки (.) и дефисы (-).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="b4d7d-112">Оно не должно быть более 1024 символов.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="b4d7d-113">Двоеточия, отображаемые в именах указывает разделение пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="b4d7d-114">Таким образом можно использовать двоеточия только для указания пространства имен XML для определенного имени.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="b4d7d-115">Кроме того необходимо придерживаться следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="b4d7d-116">Спецификации XML 1.0 оставляет за собой все имена, начинающиеся со строки «xml», любое изменение регистра символов.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="b4d7d-117">Таким образом не используйте эти имена для элемента и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="b4d7d-118">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="b4d7d-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="b4d7d-119">На практике имя должно быть как можно более короткими при по-прежнему четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="b4d7d-120">Это улучшает читаемость кода и сократить размер строки длины и исходного файла.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="b4d7d-121">Однако имя не должно быть настолько коротким, что он не описывает адекватно элемент или как код использует его.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="b4d7d-122">Это важно для удобства чтения кода.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-122">This is important for the readability of your code.</span></span> <span data-ttu-id="b4d7d-123">Если кто-то пытается найти его, или если вы самостоятельно рассматривают его длительное время после их создания, подходящие имена элементов могут сэкономить время.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="b4d7d-124">Учет регистра в именах</span><span class="sxs-lookup"><span data-stu-id="b4d7d-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="b4d7d-125">Имена элементов XML учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-125">XML element names are case sensitive.</span></span> <span data-ttu-id="b4d7d-126">Это означает, что когда компилятор Visual Basic выполняется сравнение двух имен, которые различаются только регистром алфавитный указатель, он интерпретирует их как разные имена.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="b4d7d-127">Например, он интерпретирует `ABC` и `abc` как ссылки на различные элементы.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="b4d7d-128">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="b4d7d-128">XML Namespaces</span></span>  
 <span data-ttu-id="b4d7d-129">При создании литерала элемента XML, можно указать префикс пространства имен XML для имени элемента.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="b4d7d-130">Дополнительные сведения см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d7d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b4d7d-131">See also</span></span>

- [<span data-ttu-id="b4d7d-132">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b4d7d-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b4d7d-133">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="b4d7d-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
