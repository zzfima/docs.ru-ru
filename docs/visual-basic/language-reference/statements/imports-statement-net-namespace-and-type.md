---
title: "Оператор Imports (пространство имен .NET и тип)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
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
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46cc78c2fd039fb56fd4d1b797f2d09cbe95d317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="ad448-102">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="ad448-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="ad448-103">Разрешает типа ссылаться на них без указания полного имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad448-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad448-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="ad448-105">Части</span><span class="sxs-lookup"><span data-stu-id="ad448-105">Parts</span></span>  
  
|<span data-ttu-id="ad448-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ad448-106">Term</span></span>|<span data-ttu-id="ad448-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ad448-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="ad448-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="ad448-108">Optional.</span></span> <span data-ttu-id="ad448-109">*Псевдоним импорта* или имя, по которому код может обращаться к `namespace` вместо полной строки.</span><span class="sxs-lookup"><span data-stu-id="ad448-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="ad448-110">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ad448-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="ad448-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ad448-111">Required.</span></span> <span data-ttu-id="ad448-112">Полное имя импортируемого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="ad448-113">Строка пространств имен вкладываются на любом уровне.</span><span class="sxs-lookup"><span data-stu-id="ad448-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="ad448-114">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="ad448-114">Optional.</span></span> <span data-ttu-id="ad448-115">Имя элемента программирования, объявленные в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="ad448-116">Может быть любым элементом контейнера.</span><span class="sxs-lookup"><span data-stu-id="ad448-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad448-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad448-117">Remarks</span></span>  
 <span data-ttu-id="ad448-118">`Imports` Инструкция включает типы, которые содержатся в пространстве имен напрямую ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="ad448-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="ad448-119">Можно указать имя одного пространства имен или строку из вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="ad448-120">Каждое вложенное пространство имен, разделенный точкой из следующего выше уровня пространства имен (`.`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad448-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="ad448-121">Каждый исходный файл может содержать любое количество `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ad448-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="ad448-122">Они должны следовать за любым параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать всем объявлениям программный элемент, такой как `Module` или `Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ad448-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="ad448-123">Можно использовать `Imports` только на уровне файла.</span><span class="sxs-lookup"><span data-stu-id="ad448-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="ad448-124">Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространства имен, класса, структуры, модуля, интерфейса, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="ad448-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="ad448-125">Обратите внимание, что `Imports` инструкция не делает элементы из других проектов и сборок, доступная для проекта.</span><span class="sxs-lookup"><span data-stu-id="ad448-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="ad448-126">Импорт не принимает вместо настройки ссылки.</span><span class="sxs-lookup"><span data-stu-id="ad448-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="ad448-127">Он только избавляет от необходимости уточнять имена, которые уже доступны в проект.</span><span class="sxs-lookup"><span data-stu-id="ad448-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="ad448-128">Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="ad448-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad448-129">Можно определить неявные `Imports` , используя [страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ad448-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="ad448-130">Дополнительные сведения см. в разделе [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ad448-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="ad448-131">Импорт псевдонимов</span><span class="sxs-lookup"><span data-stu-id="ad448-131">Import Aliases</span></span>  
 <span data-ttu-id="ad448-132">*Псевдоним импорта* определяет псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="ad448-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="ad448-133">Импорт псевдонимов полезны в тех случаях, когда необходимо использовать элементы с одинаковыми именами, объявленные в одну или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="ad448-134">Дополнительные сведения и пример см. в разделе «Уточнение элемент Name» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="ad448-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="ad448-135">Не следует объявлять элемента на уровне модуля с тем же именем, как `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="ad448-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="ad448-136">В противном случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.</span><span class="sxs-lookup"><span data-stu-id="ad448-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="ad448-137">Несмотря на то, что такие же синтаксис, используемый для объявления псевдонима импорта используется для импорта префикса пространства имен XML, результаты будут другими.</span><span class="sxs-lookup"><span data-stu-id="ad448-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="ad448-138">Псевдоним импорта может использоваться как выражение в коде, тогда как префикс пространства имен XML можно использовать только в XML-литералов или свойств оси XML как префикс для элемента или имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="ad448-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="ad448-139">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="ad448-139">Element Names</span></span>  
 <span data-ttu-id="ad448-140">При указании `element`, он должен представлять *элемент-контейнер*, то есть программный элемент, который может содержать другие элементы.</span><span class="sxs-lookup"><span data-stu-id="ad448-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="ad448-141">Элементы контейнера включают классы, структуры, модули, интерфейсы и перечисления.</span><span class="sxs-lookup"><span data-stu-id="ad448-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="ad448-142">Область элементов, доступных по `Imports` инструкция зависит от того, указаны ли `element`.</span><span class="sxs-lookup"><span data-stu-id="ad448-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="ad448-143">Если указать только `namespace`, однозначно все именованные члены этого пространства имен и члены элементов контейнера в этом пространстве имен, доступны без уточнения.</span><span class="sxs-lookup"><span data-stu-id="ad448-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="ad448-144">Если заданы оба `namespace` и `element`только члены этого элемента доступны без уточнения.</span><span class="sxs-lookup"><span data-stu-id="ad448-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad448-145">Пример</span><span class="sxs-lookup"><span data-stu-id="ad448-145">Example</span></span>  
 <span data-ttu-id="ad448-146">Следующий пример возвращает все папки в каталоге C:\, используя <xref:System.IO.DirectoryInfo> класса.</span><span class="sxs-lookup"><span data-stu-id="ad448-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="ad448-147">Код не имеет `Imports` инструкции в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="ad448-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="ad448-148">Таким образом `DirectoryInfo`, <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf> ссылки являются все полное с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad448-149">Пример</span><span class="sxs-lookup"><span data-stu-id="ad448-149">Example</span></span>  
 <span data-ttu-id="ad448-150">Следующий пример содержит `Imports` инструкции для пространства имен, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ad448-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="ad448-151">Таким образом типы не должны полностью соответствовать пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ad448-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad448-152">Пример</span><span class="sxs-lookup"><span data-stu-id="ad448-152">Example</span></span>  
 <span data-ttu-id="ad448-153">Следующий пример включает `Imports` инструкций, создающих псевдонимы для пространств имен на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ad448-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="ad448-154">Типы квалифицируются с псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="ad448-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="ad448-155">Пример</span><span class="sxs-lookup"><span data-stu-id="ad448-155">Example</span></span>  
 <span data-ttu-id="ad448-156">Следующий пример включает `Imports` инструкций, создающих псевдонимы для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="ad448-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="ad448-157">Псевдонимы используются для указания типов.</span><span class="sxs-lookup"><span data-stu-id="ad448-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ad448-158">См. также</span><span class="sxs-lookup"><span data-stu-id="ad448-158">See Also</span></span>  
 [<span data-ttu-id="ad448-159">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="ad448-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="ad448-160">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad448-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ad448-161">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="ad448-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="ad448-162">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="ad448-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="ad448-163">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="ad448-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
