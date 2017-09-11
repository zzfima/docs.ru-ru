---
title: "Оператор Imports (пространство имен .NET и тип) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
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
ms.openlocfilehash: af177874c3278efd348b53a2b74b4d49d6628c61
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="a3c3a-102">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="a3c3a-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="a3c3a-103">Разрешает типа ссылаться на них без квалификации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3c3a-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="a3c3a-105">Части</span><span class="sxs-lookup"><span data-stu-id="a3c3a-105">Parts</span></span>  
  
|<span data-ttu-id="a3c3a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="a3c3a-106">Term</span></span>|<span data-ttu-id="a3c3a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="a3c3a-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="a3c3a-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-108">Optional.</span></span> <span data-ttu-id="a3c3a-109">*Псевдоним импорта* или имя, по которому код может обращаться к `namespace` вместо полной строки.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="a3c3a-110">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a3c3a-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="a3c3a-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-111">Required.</span></span> <span data-ttu-id="a3c3a-112">Полное имя импортируемого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="a3c3a-113">Можно строкой пространства имен располагаться на любом уровне.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="a3c3a-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-114">Optional.</span></span> <span data-ttu-id="a3c3a-115">Имя элемента программирования, объявленного в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="a3c3a-116">Может быть любым элементом контейнера.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3c3a-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3c3a-117">Remarks</span></span>  
 <span data-ttu-id="a3c3a-118">`Imports` Инструкция включает содержащиеся в заданном пространстве имен непосредственно ссылаться на типы.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="a3c3a-119">Можно указать имя одного пространства имен или строку из вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="a3c3a-120">Каждое вложенное пространство имен отделяется от следующего уровня выше пространство имен точкой (`.`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="a3c3a-121">Каждый исходный файл может содержать любое количество `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="a3c3a-122">Они должны следовать за любым параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать любому объявлению элементов программированию, такие как `Module` или `Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="a3c3a-123">Можно использовать `Imports` только на уровне файла.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="a3c3a-124">Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространство имен, класс, структура, модуль, интерфейса, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="a3c3a-125">Обратите внимание, что `Imports` инструкция не делает элементы из других проектов и сборок, доступны в проекте.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="a3c3a-126">Импорт не выполняться ссылку.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="a3c3a-127">Он только избавляет от необходимости уточнять имена, которые уже доступны в проект.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="a3c3a-128">Дополнительные сведения см. в разделе «Импорт содержащих элементов» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c3a-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3c3a-129">Можно определить неявные `Imports` инструкций с помощью [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a3c3a-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="a3c3a-130">Дополнительные сведения см. в разделе [Практическое руководство: Добавление или удаление Импортируемые пространства имен (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).</span><span class="sxs-lookup"><span data-stu-id="a3c3a-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="a3c3a-131">Импорт псевдонимов</span><span class="sxs-lookup"><span data-stu-id="a3c3a-131">Import Aliases</span></span>  
 <span data-ttu-id="a3c3a-132">*Псевдоним импорта* определяет псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="a3c3a-133">Псевдонимы применяются, когда необходимо использовать элементы с одинаковыми именами, объявленные в одну или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="a3c3a-134">Дополнительные сведения и пример см. в разделе «Определение элемента Name» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c3a-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="a3c3a-135">Не следует объявлять элемент на уровне модуля с тем же именем, как `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="a3c3a-136">В противном случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="a3c3a-137">Хотя синтаксис, используемый для объявления псевдонима импорта подобного используется для импорта префикса пространства имен XML, результаты будут другими.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="a3c3a-138">Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML-литералов или свойств оси XML как префикс для элемента или имени атрибута.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="a3c3a-139">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="a3c3a-139">Element Names</span></span>  
 <span data-ttu-id="a3c3a-140">При указании `element`, он должен представлять *элемент-контейнер*, то есть элемент программирования, может содержать другие элементы.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="a3c3a-141">Элементы контейнера включают классы, структуры, модули, интерфейсы и перечисления.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="a3c3a-142">Область элементов, доступных по `Imports` инструкция зависит от того, указаны ли `element`.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="a3c3a-143">Если указать только `namespace`, однозначно все члены этого пространства имен и члены элементов контейнера в этом пространстве имен, доступны без уточнения.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="a3c3a-144">Если указываются оба `namespace` и `element`только члены этого элемента будут доступны без уточнения.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c3a-145">Пример</span><span class="sxs-lookup"><span data-stu-id="a3c3a-145">Example</span></span>  
 <span data-ttu-id="a3c3a-146">Следующий пример возвращает все папки в каталоге C:\ с помощью <xref:System.IO.DirectoryInfo>класса.</xref:System.IO.DirectoryInfo></span><span class="sxs-lookup"><span data-stu-id="a3c3a-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="a3c3a-147">Код не имеет `Imports` в начало файла.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="a3c3a-148">Таким образом `DirectoryInfo`, <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf>ссылки являются полностью полного пространства имен.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="a3c3a-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="a3c3a-149">[!code-vb[VbVbalrStatements&#152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-149">[!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c3a-150">Пример</span><span class="sxs-lookup"><span data-stu-id="a3c3a-150">Example</span></span>  
 <span data-ttu-id="a3c3a-151">Следующий пример включает `Imports` инструкции для пространств имен, на которые имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-151">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="a3c3a-152">Таким образом типы не должны полностью соответствовать пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-152">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 <span data-ttu-id="a3c3a-153">[!code-vb[VbVbalrStatements&#153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-153">[!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]</span></span>  
  
 <span data-ttu-id="a3c3a-154">[!code-vb[VbVbalrStatements&#154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-154">[!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c3a-155">Пример</span><span class="sxs-lookup"><span data-stu-id="a3c3a-155">Example</span></span>  
 <span data-ttu-id="a3c3a-156">Следующий пример включает `Imports` инструкции, создающие псевдонимы для пространств имен, на которые имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-156">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="a3c3a-157">Типы будут дополнены псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-157">The types are qualified with the aliases.</span></span>  
  
 <span data-ttu-id="a3c3a-158">[!code-vb[VbVbalrStatements&#155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-158">[!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]</span></span>  
  
 <span data-ttu-id="a3c3a-159">[!code-vb[VbVbalrStatements&#156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-159">[!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c3a-160">Пример</span><span class="sxs-lookup"><span data-stu-id="a3c3a-160">Example</span></span>  
 <span data-ttu-id="a3c3a-161">Следующий пример включает `Imports` инструкции, создающие псевдонимы для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-161">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="a3c3a-162">Псевдонимы используются для указания типов.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-162">Aliases are used to specify the types.</span></span>  
  
 <span data-ttu-id="a3c3a-163">[!code-vb[VbVbalrStatements&#157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-163">[!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]</span></span>  
  
 <span data-ttu-id="a3c3a-164">[!code-vb[VbVbalrStatements&#158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a3c3a-164">[!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c3a-165">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c3a-165">See Also</span></span>  
 <span data-ttu-id="a3c3a-166">[Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a3c3a-166">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="a3c3a-167"> [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="a3c3a-167"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="a3c3a-168"> [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a3c3a-168"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="a3c3a-169"> [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="a3c3a-169"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="a3c3a-170"> [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="a3c3a-170"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
