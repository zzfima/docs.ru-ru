---
title: "Введите повышение (Visual Basic) | Документы Microsoft"
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
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
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
ms.openlocfilehash: 383f4b1d29e9bbf81eee44bf78762a80aea9eb36
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="cb83e-102">Повышение типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb83e-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="cb83e-103">При объявлении элемента программирования в модуле, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] повышает уровень его области до пространства имен, содержащего модуль.</span><span class="sxs-lookup"><span data-stu-id="cb83e-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="cb83e-104">Это называется *введите повышения*.</span><span class="sxs-lookup"><span data-stu-id="cb83e-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="cb83e-105">В следующем примере показано определение схемы модуля и двух членов этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cb83e-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 <span data-ttu-id="cb83e-106">[!code-vb[VbVbalrDeclaredElements&#1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb83e-106">[!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span></span>  
  
 <span data-ttu-id="cb83e-107">В `projModule`, программирования элементы, объявленные на уровне модуля, продвигаются в `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="cb83e-107">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="cb83e-108">В предыдущем примере `basicEnum` и `innerClass` повышаются, но `numberSub` — нет, поскольку он не объявлен на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="cb83e-108">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="cb83e-109">Эффект повышения типа</span><span class="sxs-lookup"><span data-stu-id="cb83e-109">Effect of Type Promotion</span></span>  
 <span data-ttu-id="cb83e-110">Эффект повышения типа является то, что уточняющую строку не нужно включать имя модуля.</span><span class="sxs-lookup"><span data-stu-id="cb83e-110">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="cb83e-111">Следующий пример вызывает две процедуры в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="cb83e-111">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 <span data-ttu-id="cb83e-112">[!code-vb[VbVbalrDeclaredElements&#2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb83e-112">[!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span></span>  
  
 <span data-ttu-id="cb83e-113">В предыдущем примере для первого вызова используются полные квалификационные строки.</span><span class="sxs-lookup"><span data-stu-id="cb83e-113">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="cb83e-114">Однако это не требуется из-за повышения типов.</span><span class="sxs-lookup"><span data-stu-id="cb83e-114">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="cb83e-115">Во втором вызове также доступ к членам модуля без включения `projModule` в строки квалификации.</span><span class="sxs-lookup"><span data-stu-id="cb83e-115">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="cb83e-116">Отмена повышения типа</span><span class="sxs-lookup"><span data-stu-id="cb83e-116">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="cb83e-117">Если пространство имен уже содержит член с тем же именем члена модуля, повышение типа для члена модуля отменяется.</span><span class="sxs-lookup"><span data-stu-id="cb83e-117">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="cb83e-118">Следующий пример показывает определение схемы перечисления и модуль в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="cb83e-118">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 <span data-ttu-id="cb83e-119">[!code-vb[VbVbalrDeclaredElements&#3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb83e-119">[!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span></span>  
  
 <span data-ttu-id="cb83e-120">В предыдущем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не удается повысить уровень класса `abc` для `thisNameSpace` , поскольку уже существует перечисление с тем же именем на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb83e-120">In the preceding example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="cb83e-121">Чтобы получить доступ к `abcSub`, необходимо использовать полное имя пространства имен строка `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="cb83e-121">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="cb83e-122">Тем не менее, класс `xyz` по-прежнему повышается, и можно получить доступ к `xyzSub` с короткой строки квалификации `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="cb83e-122">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="cb83e-123">Отмена повышения типа для разделяемых типов</span><span class="sxs-lookup"><span data-stu-id="cb83e-123">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="cb83e-124">Если класс или структуру в модуле использует [частичного](../../../../visual-basic/language-reference/modifiers/partial.md) ключевое слово, повышение типа является невозможным для этого класса или структуры, ли пространство имен содержит член с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="cb83e-124">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="cb83e-125">Других элементов в модуле повышение типа по-прежнему возможно.</span><span class="sxs-lookup"><span data-stu-id="cb83e-125">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="cb83e-126">**Последствия.**</span><span class="sxs-lookup"><span data-stu-id="cb83e-126">**Consequences.**</span></span> <span data-ttu-id="cb83e-127">Отмена повышения типа частичного определения может привести к непредсказуемым результатам и даже ошибкам компилятора.</span><span class="sxs-lookup"><span data-stu-id="cb83e-127">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="cb83e-128">Следующий пример показывает каркас определения разделяемого класса, один из которых находится внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="cb83e-128">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 <span data-ttu-id="cb83e-129">[!code-vb[VbVbalrDeclaredElements&#4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb83e-129">[!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span></span>  
  
 <span data-ttu-id="cb83e-130">В предыдущем примере разработчик может ожидать, что компилятор слияние двух частично выполненных определений `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="cb83e-130">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="cb83e-131">Тем не менее, компилятор не учитывает частичное определение внутри акции `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="cb83e-131">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="cb83e-132">В результате он попытается скомпилировать два отдельных и различных класса, обе с именем `sampleClass` , но с разными квалификационными путями.</span><span class="sxs-lookup"><span data-stu-id="cb83e-132">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="cb83e-133">Компилятор объединяет частичные определения, только если их полные пути идентичны.</span><span class="sxs-lookup"><span data-stu-id="cb83e-133">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="cb83e-134">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="cb83e-134">Recommendations</span></span>  
 <span data-ttu-id="cb83e-135">Следующие рекомендации представляют рекомендаций программирования.</span><span class="sxs-lookup"><span data-stu-id="cb83e-135">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="cb83e-136">**Уникальные имена.**</span><span class="sxs-lookup"><span data-stu-id="cb83e-136">**Unique Names.**</span></span> <span data-ttu-id="cb83e-137">Если у вас есть полный контроль над именованием элементов программирования, рекомендуется всегда использовать уникальные имена везде.</span><span class="sxs-lookup"><span data-stu-id="cb83e-137">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="cb83e-138">Одинаковые имена требуют дополнительного уточнения и могут сделать код трудным для чтения.</span><span class="sxs-lookup"><span data-stu-id="cb83e-138">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="cb83e-139">Они также может привести к непредсказуемым результатам и опасным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="cb83e-139">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="cb83e-140">**Полное имя пространства имен.**</span><span class="sxs-lookup"><span data-stu-id="cb83e-140">**Full Qualification.**</span></span> <span data-ttu-id="cb83e-141">При работе с модулями и другими элементами в одном пространстве имен безопаснее использовать полное определение для всех элементов программирования.</span><span class="sxs-lookup"><span data-stu-id="cb83e-141">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="cb83e-142">Если повышение типа для члена модуля отменяется, а не полностью соответствуют этому элементу, может случайно доступ к другому элементу программирования.</span><span class="sxs-lookup"><span data-stu-id="cb83e-142">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb83e-143">См. также</span><span class="sxs-lookup"><span data-stu-id="cb83e-143">See Also</span></span>  
 <span data-ttu-id="cb83e-144">[Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cb83e-144">[Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="cb83e-145"> [Оператор Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cb83e-145"> [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="cb83e-146"> [Частичное](../../../../visual-basic/language-reference/modifiers/partial.md) </span><span class="sxs-lookup"><span data-stu-id="cb83e-146"> [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) </span></span>  
<span data-ttu-id="cb83e-147"> [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="cb83e-147"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="cb83e-148"> [Практическое руководство: управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="cb83e-148"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="cb83e-149"> [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="cb83e-149"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
