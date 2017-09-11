---
title: "Атрибут списка (Visual Basic) | Документы Microsoft"
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
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 6aea239e2e0d8a266b8eb6ba2876fb109e077c46
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="9f0f2-102">Список атрибутов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f0f2-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="9f0f2-103">Указывает атрибуты, применяемые к объявленному программному элементу.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="9f0f2-104">Несколько атрибутов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="9f0f2-105">Ниже приведен синтаксис для одного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0f2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f0f2-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="9f0f2-107">Части</span><span class="sxs-lookup"><span data-stu-id="9f0f2-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="9f0f2-108">Обязательный для атрибутов, примененных в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="9f0f2-109">Может быть [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) или [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="9f0f2-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="9f0f2-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-110">Required.</span></span> <span data-ttu-id="9f0f2-111">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="9f0f2-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-112">Optional.</span></span> <span data-ttu-id="9f0f2-113">Список позиционных аргументов для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="9f0f2-114">Несколько аргументов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="9f0f2-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-115">Optional.</span></span> <span data-ttu-id="9f0f2-116">Список инициализаторов переменных или свойств для данного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="9f0f2-117">Несколько инициализаторов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f0f2-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f0f2-118">Remarks</span></span>  
 <span data-ttu-id="9f0f2-119">Можно применить один или несколько атрибутов практически любого элементу программирования (типы, процедуры, свойства и т. д.).</span><span class="sxs-lookup"><span data-stu-id="9f0f2-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="9f0f2-120">Атрибуты отображаются в метаданных сборки и они могут помочь комментировать код или указать способ использования конкретного элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="9f0f2-121">Можно применить атрибуты, определенные в Visual Basic и .NET Framework, и можно определить собственные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="9f0f2-122">Дополнительные сведения об использовании атрибутов см. в разделе [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f0f2-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="9f0f2-123">Сведения об именах атрибутов в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9f0f2-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9f0f2-124">Правила</span><span class="sxs-lookup"><span data-stu-id="9f0f2-124">Rules</span></span>  
  
-   <span data-ttu-id="9f0f2-125">**Размещение.**</span><span class="sxs-lookup"><span data-stu-id="9f0f2-125">**Placement.**</span></span> <span data-ttu-id="9f0f2-126">Можно применить атрибуты к большинству объявленных элементов программирования.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="9f0f2-127">Чтобы применить один или несколько атрибутов, поместите *блок атрибута* в начале объявления элемента.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="9f0f2-128">Каждая запись в списке атрибутов задает атрибут, который вы хотите применить и модификатор и аргументы, которые вы используете для этого вызова этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="9f0f2-129">**Угловые скобки.**</span><span class="sxs-lookup"><span data-stu-id="9f0f2-129">**Angle Brackets.**</span></span> <span data-ttu-id="9f0f2-130">Если указан список атрибутов, его необходимо заключить в угловые скобки («`<`«и»`>`»).</span><span class="sxs-lookup"><span data-stu-id="9f0f2-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="9f0f2-131">**Часть объявления.**</span><span class="sxs-lookup"><span data-stu-id="9f0f2-131">**Part of the Declaration.**</span></span> <span data-ttu-id="9f0f2-132">Атрибут должен быть частью объявления элемента, а не отдельной инструкции.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="9f0f2-133">Можно использовать последовательность продолжения строки (« `_`») для расширения оператора объявления на несколько строк исходного кода.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="9f0f2-134">**Модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="9f0f2-134">**Modifiers.**</span></span> <span data-ttu-id="9f0f2-135">Модификатор атрибута (`Assembly` или `Module`) необходим для каждого атрибута, примененного к элементу программирования в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="9f0f2-136">Модификаторы атрибутов не допускаются для атрибутов, примененных к элементам, которые не в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="9f0f2-137">**Аргументы.**</span><span class="sxs-lookup"><span data-stu-id="9f0f2-137">**Arguments.**</span></span> <span data-ttu-id="9f0f2-138">Все позиционные аргументы атрибута должны предшествовать инициализаторам любой переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f0f2-139">Пример</span><span class="sxs-lookup"><span data-stu-id="9f0f2-139">Example</span></span>  
 <span data-ttu-id="9f0f2-140">В следующем примере применяется <xref:System.Runtime.InteropServices.DllImportAttribute>атрибут определение схемы `Function` процедуры.</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="9f0f2-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 <span data-ttu-id="9f0f2-141">[!code-vb[VbVbalrStatements&#1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9f0f2-141">[!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]</span></span>  
  
 <span data-ttu-id="9f0f2-142"><xref:System.Runtime.InteropServices.DllImportAttribute>Указывает, что процедура атрибутами представляет точку входа в неуправляемой библиотеки динамической компоновки (DLL).</xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="9f0f2-142"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="9f0f2-143">Атрибут предоставляет имя DLL как позиционные аргументы и другие сведения — как инициализаторы переменных.</span><span class="sxs-lookup"><span data-stu-id="9f0f2-143">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0f2-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9f0f2-144">See Also</span></span>  
 <span data-ttu-id="9f0f2-145">[Сборки](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f2-145">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="9f0f2-146"> [Модуль \<ключевое слово настроек](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f2-146"> [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="9f0f2-147"> [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f2-147"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="9f0f2-148"> [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="9f0f2-148"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>

