---
title: Оператор Imports — пространство имен и тип .NET (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912391"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="83f8f-102">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="83f8f-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="83f8f-103">Позволяет ссылаться на имена типов без уточнения пространства имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83f8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83f8f-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="83f8f-105">Части</span><span class="sxs-lookup"><span data-stu-id="83f8f-105">Parts</span></span>  
  
|<span data-ttu-id="83f8f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="83f8f-106">Term</span></span>|<span data-ttu-id="83f8f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="83f8f-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="83f8f-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="83f8f-108">Optional.</span></span> <span data-ttu-id="83f8f-109">Псевдоним или имя *импорта* , по которому может ссылаться `namespace` код вместо полной уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="83f8f-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="83f8f-110">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="83f8f-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="83f8f-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="83f8f-111">Required.</span></span> <span data-ttu-id="83f8f-112">Полное имя импортируемого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="83f8f-113">Может быть строкой пространств имен, вложенных в любой уровень.</span><span class="sxs-lookup"><span data-stu-id="83f8f-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="83f8f-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="83f8f-114">Optional.</span></span> <span data-ttu-id="83f8f-115">Имя программного элемента, объявленного в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="83f8f-116">Может быть любым элементом контейнера.</span><span class="sxs-lookup"><span data-stu-id="83f8f-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83f8f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="83f8f-117">Remarks</span></span>  
 <span data-ttu-id="83f8f-118">`Imports` Оператор позволяет напрямую ссылаться на типы, содержащиеся в данном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="83f8f-119">Можно указать одно имя пространства имен или строку вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="83f8f-120">Каждое вложенное пространство имен отделяется от следующего пространства имен более высокого уровня точкой`.`(), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="83f8f-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="83f8f-121">Каждый исходный файл может содержать любое количество `Imports` инструкций.</span><span class="sxs-lookup"><span data-stu-id="83f8f-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="83f8f-122">Они должны следовать любым объявлениям параметров, таким как `Option Strict` оператор, и должны предшествовать любым объявлениям элементов программирования, таким как `Module` операторы или `Class` .</span><span class="sxs-lookup"><span data-stu-id="83f8f-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="83f8f-123">Можно использовать `Imports` только на уровне файлов.</span><span class="sxs-lookup"><span data-stu-id="83f8f-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="83f8f-124">Это означает, что контекст объявления для импорта должен быть исходным файлом и не может быть пространством имен, классом, структурой, модулем, интерфейсом, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="83f8f-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="83f8f-125">Обратите внимание `Imports` , что инструкция не делает элементы из других проектов и сборок доступными для проекта.</span><span class="sxs-lookup"><span data-stu-id="83f8f-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="83f8f-126">Импорт не является местом установки ссылки.</span><span class="sxs-lookup"><span data-stu-id="83f8f-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="83f8f-127">Он только устраняет необходимость уточнять имена, которые уже доступны для проекта.</span><span class="sxs-lookup"><span data-stu-id="83f8f-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="83f8f-128">Дополнительные сведения см. в разделе "Импорт содержащихся элементов" в [ссылках на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="83f8f-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83f8f-129">Неявные `Imports` инструкции можно определить с помощью [страницы ссылки в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="83f8f-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="83f8f-130">Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление импортированных пространств имен (Visual Basic](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)).</span><span class="sxs-lookup"><span data-stu-id="83f8f-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="83f8f-131">Импорт псевдонимов</span><span class="sxs-lookup"><span data-stu-id="83f8f-131">Import Aliases</span></span>  
 <span data-ttu-id="83f8f-132">*Псевдоним импорта* определяет псевдоним для пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="83f8f-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="83f8f-133">Псевдонимы импорта полезны, когда необходимо использовать элементы с одинаковыми именами, объявленными в одном или нескольких пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="83f8f-134">Дополнительные сведения и пример см. в разделе "уточнение имени элемента в ссылках [на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)".</span><span class="sxs-lookup"><span data-stu-id="83f8f-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="83f8f-135">Не следует объявлять элемент на уровне модуля с тем же именем, что `aliasname`и.</span><span class="sxs-lookup"><span data-stu-id="83f8f-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="83f8f-136">В этом случае компилятор Visual Basic использует `aliasname` только для объявленного элемента и больше не распознает его как псевдоним импорта.</span><span class="sxs-lookup"><span data-stu-id="83f8f-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="83f8f-137">Хотя синтаксис, используемый для объявления псевдонима импорта, похож на тот, который используется для импорта префикса пространства имен XML, результаты различаются.</span><span class="sxs-lookup"><span data-stu-id="83f8f-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="83f8f-138">Псевдоним импорта можно использовать как выражение в коде, тогда как префикс пространства имен XML можно использовать только в литералах XML или свойствах оси XML в качестве префикса для полного имени элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="83f8f-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="83f8f-139">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="83f8f-139">Element Names</span></span>  
 <span data-ttu-id="83f8f-140">При указании `element`он должен представлять элемент- *контейнер*, то есть программный элемент, который может содержать другие элементы.</span><span class="sxs-lookup"><span data-stu-id="83f8f-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="83f8f-141">Контейнерные элементы включают классы, структуры, модули, интерфейсы и перечисления.</span><span class="sxs-lookup"><span data-stu-id="83f8f-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="83f8f-142">Область действия элементов, доступных для `Imports` инструкции, зависит от того, указан `element`ли параметр.</span><span class="sxs-lookup"><span data-stu-id="83f8f-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="83f8f-143">Если указать только `namespace`, то все члены этого пространства имен с уникальными именами и элементы контейнеров внутри этого пространства имен будут доступны без квалификации.</span><span class="sxs-lookup"><span data-stu-id="83f8f-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="83f8f-144">Если указать `namespace` и, и `element`, то только элементы этого элемента будут доступны без квалификации.</span><span class="sxs-lookup"><span data-stu-id="83f8f-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83f8f-145">Пример</span><span class="sxs-lookup"><span data-stu-id="83f8f-145">Example</span></span>  
 <span data-ttu-id="83f8f-146">В следующем примере возвращаются все папки в папке C:\. каталог с помощью <xref:System.IO.DirectoryInfo> класса.</span><span class="sxs-lookup"><span data-stu-id="83f8f-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="83f8f-147">Код не содержит `Imports` операторов в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="83f8f-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="83f8f-148">Таким образом, `DirectoryInfo`ссылки <xref:System.Text.StringBuilder>, и <xref:Microsoft.VisualBasic.ControlChars.CrLf> полностью определены с помощью пространств имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="83f8f-149">Пример</span><span class="sxs-lookup"><span data-stu-id="83f8f-149">Example</span></span>  
 <span data-ttu-id="83f8f-150">В следующем примере содержатся `Imports` инструкции для пространств имен, на которые имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="83f8f-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="83f8f-151">Поэтому типы не обязательно должны быть полными с помощью пространств имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="83f8f-152">Пример</span><span class="sxs-lookup"><span data-stu-id="83f8f-152">Example</span></span>  
 <span data-ttu-id="83f8f-153">В следующем примере содержатся `Imports` инструкции, создающие псевдонимы для упоминаемых пространств имен.</span><span class="sxs-lookup"><span data-stu-id="83f8f-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="83f8f-154">Типы дополнены псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="83f8f-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="83f8f-155">Пример</span><span class="sxs-lookup"><span data-stu-id="83f8f-155">Example</span></span>  
 <span data-ttu-id="83f8f-156">В следующем примере содержатся `Imports` инструкции, создающие псевдонимы для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="83f8f-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="83f8f-157">Для указания типов используются псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="83f8f-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="83f8f-158">См. также</span><span class="sxs-lookup"><span data-stu-id="83f8f-158">See also</span></span>

- [<span data-ttu-id="83f8f-159">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="83f8f-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="83f8f-160">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83f8f-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="83f8f-161">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="83f8f-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="83f8f-162">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="83f8f-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="83f8f-163">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="83f8f-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
