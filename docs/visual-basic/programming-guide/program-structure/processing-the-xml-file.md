---
title: Обработка XML-файла (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d44f58951d99f1b4b551af75dc0a0e895e337e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="75438-102">Обработка XML-файла (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75438-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="75438-103">Компилятор создает строку идентификатора для каждой конструкции в коде, помеченной для создания документации.</span><span class="sxs-lookup"><span data-stu-id="75438-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="75438-104">(Сведения о том, как для маркировки кода см. в разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Строка идентификатора однозначно определяет конструкцию.</span><span class="sxs-lookup"><span data-stu-id="75438-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="75438-105">Программы обработки XML-файла можно использовать строку идентификатора для идентификации соответствующего [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] элемента метаданных или отражения.</span><span class="sxs-lookup"><span data-stu-id="75438-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="75438-106">XML-файл не представляет собой иерархическое представление кода; Это список с созданным Идентификатором для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="75438-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="75438-107">Компилятор соблюдает следующие правила при формировании строк идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="75438-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="75438-108">Без пробелов помещается в строку.</span><span class="sxs-lookup"><span data-stu-id="75438-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="75438-109">Первая часть строки идентификатора определяет тип члена идентифицируется в виде одного символа, за которым следует двоеточие.</span><span class="sxs-lookup"><span data-stu-id="75438-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="75438-110">Используются следующие типы членов.</span><span class="sxs-lookup"><span data-stu-id="75438-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="75438-111">Знак</span><span class="sxs-lookup"><span data-stu-id="75438-111">Character</span></span>|<span data-ttu-id="75438-112">Описание</span><span class="sxs-lookup"><span data-stu-id="75438-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="75438-113">в</span><span class="sxs-lookup"><span data-stu-id="75438-113">N</span></span>|<span data-ttu-id="75438-114">namespace</span><span class="sxs-lookup"><span data-stu-id="75438-114">namespace</span></span><br /><br /> <span data-ttu-id="75438-115">Не удается добавить комментарии к документации к пространству имен, но можно сделать CREF ссылки на них, если она поддерживается.</span><span class="sxs-lookup"><span data-stu-id="75438-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="75438-116">T</span><span class="sxs-lookup"><span data-stu-id="75438-116">T</span></span>|<span data-ttu-id="75438-117">Тип: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="75438-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="75438-118">C</span><span class="sxs-lookup"><span data-stu-id="75438-118">F</span></span>|<span data-ttu-id="75438-119">поле:`Dim`</span><span class="sxs-lookup"><span data-stu-id="75438-119">field: `Dim`</span></span>|  
|<span data-ttu-id="75438-120">С</span><span class="sxs-lookup"><span data-stu-id="75438-120">P</span></span>|<span data-ttu-id="75438-121">свойство: `Property` (включая свойства по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="75438-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="75438-122">M</span><span class="sxs-lookup"><span data-stu-id="75438-122">M</span></span>|<span data-ttu-id="75438-123">метод: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="75438-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="75438-124">E</span><span class="sxs-lookup"><span data-stu-id="75438-124">E</span></span>|<span data-ttu-id="75438-125">событие:`Event`</span><span class="sxs-lookup"><span data-stu-id="75438-125">event: `Event`</span></span>|  
|<span data-ttu-id="75438-126">!</span><span class="sxs-lookup"><span data-stu-id="75438-126">!</span></span>|<span data-ttu-id="75438-127">текст ошибки</span><span class="sxs-lookup"><span data-stu-id="75438-127">error string</span></span><br /><br /> <span data-ttu-id="75438-128">Остальная часть строки предоставляет сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="75438-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="75438-129">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор создает сведения об ошибках для ссылок, которые не удается разрешить.</span><span class="sxs-lookup"><span data-stu-id="75438-129">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="75438-130">Во второй части `String` — полное имя элемента, начиная с корневого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="75438-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="75438-131">Имя элемента, включающий его тип и пространство имен разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="75438-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="75438-132">Если имя элемента содержит точки, они заменяются знаком решетки (#).</span><span class="sxs-lookup"><span data-stu-id="75438-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="75438-133">Предполагается, что элемент не имеет знака непосредственно в имени.</span><span class="sxs-lookup"><span data-stu-id="75438-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="75438-134">Например, полное имя `String` бы конструктор `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="75438-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="75438-135">Для свойств и методов, имеющих аргументы, список этих аргументов заключается в круглые скобки и указывается в конце.</span><span class="sxs-lookup"><span data-stu-id="75438-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="75438-136">Если аргументы не используются, скобки отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="75438-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="75438-137">Аргументы разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="75438-137">The arguments are separated by commas.</span></span> <span data-ttu-id="75438-138">Кодировка каждого аргумента следует непосредственно из того, как он кодируется в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] подписи.</span><span class="sxs-lookup"><span data-stu-id="75438-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75438-139">Пример</span><span class="sxs-lookup"><span data-stu-id="75438-139">Example</span></span>  
 <span data-ttu-id="75438-140">В следующем коде показано, как идентификатор строки для класса и его членов, создаются.</span><span class="sxs-lookup"><span data-stu-id="75438-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="75438-141">См. также</span><span class="sxs-lookup"><span data-stu-id="75438-141">See Also</span></span>  
 [<span data-ttu-id="75438-142">/doc</span><span class="sxs-lookup"><span data-stu-id="75438-142">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="75438-143">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="75438-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
