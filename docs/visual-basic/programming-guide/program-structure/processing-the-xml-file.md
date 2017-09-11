---
title: "Обработка XML-файла (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
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
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="59584-102">Обработка XML-файла (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59584-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="59584-103">Компилятор создает строку идентификатора для каждой конструкции в коде, отмеченной для создания документации.</span><span class="sxs-lookup"><span data-stu-id="59584-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="59584-104">(Сведения о том, как для маркировки кода в разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Строка идентификатора однозначно определяет конструкцию.</span><span class="sxs-lookup"><span data-stu-id="59584-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="59584-105">Программы обработки XML-файла можно использовать строку идентификатора для идентификации соответствующего [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] элемента метаданных или отражения.</span><span class="sxs-lookup"><span data-stu-id="59584-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="59584-106">XML-файл не является иерархическое представление кода; он содержит список с созданным Идентификатором для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="59584-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="59584-107">Компилятор должно соответствовать следующим правилам при формировании строк Идентификаторов:</span><span class="sxs-lookup"><span data-stu-id="59584-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="59584-108">Отсутствует пробел не помещается в строку.</span><span class="sxs-lookup"><span data-stu-id="59584-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="59584-109">Первая часть строки идентификатора определяет тип члена, идентифицированного в виде одного символа, за которым следует двоеточие.</span><span class="sxs-lookup"><span data-stu-id="59584-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="59584-110">Используются следующие типы элементов.</span><span class="sxs-lookup"><span data-stu-id="59584-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="59584-111">Знак</span><span class="sxs-lookup"><span data-stu-id="59584-111">Character</span></span>|<span data-ttu-id="59584-112">Описание</span><span class="sxs-lookup"><span data-stu-id="59584-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="59584-113">в</span><span class="sxs-lookup"><span data-stu-id="59584-113">N</span></span>|<span data-ttu-id="59584-114">namespace</span><span class="sxs-lookup"><span data-stu-id="59584-114">namespace</span></span><br /><br /> <span data-ttu-id="59584-115">Нельзя добавлять комментарии документации к пространству имен, но можно сделать CREF-ссылки на них, если они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="59584-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="59584-116">T</span><span class="sxs-lookup"><span data-stu-id="59584-116">T</span></span>|<span data-ttu-id="59584-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="59584-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="59584-118">C</span><span class="sxs-lookup"><span data-stu-id="59584-118">F</span></span>|<span data-ttu-id="59584-119">поле:`Dim`</span><span class="sxs-lookup"><span data-stu-id="59584-119">field: `Dim`</span></span>|  
|<span data-ttu-id="59584-120">С</span><span class="sxs-lookup"><span data-stu-id="59584-120">P</span></span>|<span data-ttu-id="59584-121">свойство: `Property` (включая свойства по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="59584-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="59584-122">M</span><span class="sxs-lookup"><span data-stu-id="59584-122">M</span></span>|<span data-ttu-id="59584-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="59584-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="59584-124">E</span><span class="sxs-lookup"><span data-stu-id="59584-124">E</span></span>|<span data-ttu-id="59584-125">событие:`Event`</span><span class="sxs-lookup"><span data-stu-id="59584-125">event: `Event`</span></span>|  
|<span data-ttu-id="59584-126">!</span><span class="sxs-lookup"><span data-stu-id="59584-126">!</span></span>|<span data-ttu-id="59584-127">Строка ошибки</span><span class="sxs-lookup"><span data-stu-id="59584-127">error string</span></span><br /><br /> <span data-ttu-id="59584-128">Остальная часть строки предоставляет сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="59584-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="59584-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор создает сведения об ошибках для ссылок, которые не удается разрешить.</span><span class="sxs-lookup"><span data-stu-id="59584-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="59584-130">Во второй части `String` полное имя элемента, начиная с корневого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="59584-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="59584-131">Имя элемента, включающий его тип и пространство имен разделяются точками.</span><span class="sxs-lookup"><span data-stu-id="59584-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="59584-132">Если имя элемента содержит точки, они заменяются знаком решетки (#).</span><span class="sxs-lookup"><span data-stu-id="59584-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="59584-133">Предполагается, что элемент не имеет знак решетки непосредственно в имени.</span><span class="sxs-lookup"><span data-stu-id="59584-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="59584-134">Например, полное имя `String` бы конструктор `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="59584-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="59584-135">Для свойств и методов при наличии аргументов методу, следует список аргументов, заключенный в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="59584-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="59584-136">Если не указано никаких аргументов, скобки отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="59584-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="59584-137">Аргументы разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="59584-137">The arguments are separated by commas.</span></span> <span data-ttu-id="59584-138">Кодировка каждого аргумента следует непосредственно из того, как он кодируется в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] подписи.</span><span class="sxs-lookup"><span data-stu-id="59584-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59584-139">Пример</span><span class="sxs-lookup"><span data-stu-id="59584-139">Example</span></span>  
 <span data-ttu-id="59584-140">В следующем коде показано, как идентификатор строки для класса и его членов, создаются.</span><span class="sxs-lookup"><span data-stu-id="59584-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="59584-141">[!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="59584-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59584-142">См. также</span><span class="sxs-lookup"><span data-stu-id="59584-142">See Also</span></span>  
 <span data-ttu-id="59584-143">[/ doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="59584-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="59584-144"> [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="59584-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
