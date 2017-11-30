---
title: "Повышение типа (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="2595b-102">Повышение типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2595b-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="2595b-103">При объявлении элемента программирования в модуле, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] повышает уровень его области пространства имен, содержащего модуль.</span><span class="sxs-lookup"><span data-stu-id="2595b-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="2595b-104">Это называется *введите рекламной акции*.</span><span class="sxs-lookup"><span data-stu-id="2595b-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="2595b-105">В следующем примере показано определение схемы модуля и двух членов этого модуля.</span><span class="sxs-lookup"><span data-stu-id="2595b-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="2595b-106">В пределах `projModule`программирования элементы, объявленные на уровне модуля, продвигаются в `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="2595b-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="2595b-107">В приведенном выше примере `basicEnum` и `innerClass` отправит запрос, но `numberSub` — нет, поскольку он не объявлен как на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="2595b-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="2595b-108">Эффект повышения типа</span><span class="sxs-lookup"><span data-stu-id="2595b-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="2595b-109">Повышение типа действует, уточняющей строки не должны включать имя модуля.</span><span class="sxs-lookup"><span data-stu-id="2595b-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="2595b-110">Следующий пример вызывает две процедуры в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="2595b-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="2595b-111">В предыдущем примере первый вызов использует квалификации завершения строки.</span><span class="sxs-lookup"><span data-stu-id="2595b-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="2595b-112">Однако это не требуется из-за повышения типов.</span><span class="sxs-lookup"><span data-stu-id="2595b-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="2595b-113">Во втором вызове также доступ к членам модуля без включения `projModule` в строки квалификации.</span><span class="sxs-lookup"><span data-stu-id="2595b-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="2595b-114">Отмена повышения типа</span><span class="sxs-lookup"><span data-stu-id="2595b-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="2595b-115">Если пространство имен уже имеется член с тем же именем члена модуля, повышение типа для члена модуля отменяется.</span><span class="sxs-lookup"><span data-stu-id="2595b-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="2595b-116">В следующем примере показано каркасное определение перечисления и модуль в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="2595b-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="2595b-117">В приведенном выше примере [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] невозможно повысить уровень класса `abc` для `thisNameSpace` , так как уже существует перечисление с тем же именем на уровне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2595b-117">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="2595b-118">Чтобы получить доступ к `abcSub`, необходимо использовать полной строки `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="2595b-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="2595b-119">Однако для класса `xyz` по-прежнему повышается, и имеет доступ к `xyzSub` с более короткие строки квалификации `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="2595b-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="2595b-120">Отмена повышения типа для разделяемых типов</span><span class="sxs-lookup"><span data-stu-id="2595b-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="2595b-121">Если класс или структуру в модуле использует [частичного](../../../../visual-basic/language-reference/modifiers/partial.md) ключевое слово, повышение типа автоматически отменяется для этого класса или структуры, независимо от того, имеется ли пространство имен содержит член с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="2595b-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="2595b-122">Другие элементы в модуль, по-прежнему возможно повышение типа.</span><span class="sxs-lookup"><span data-stu-id="2595b-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="2595b-123">**Последствия.**</span><span class="sxs-lookup"><span data-stu-id="2595b-123">**Consequences.**</span></span> <span data-ttu-id="2595b-124">Отмена повышения типа частичного определения может привести к непредсказуемым результатам и даже ошибкам компилятора.</span><span class="sxs-lookup"><span data-stu-id="2595b-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="2595b-125">В следующем примере каркас разделяемые определения класса, один из которых находится внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="2595b-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="2595b-126">В предыдущем примере разработчик может ожидать, что компилятор слияние двух частично выполненных определений `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="2595b-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="2595b-127">Однако компилятор не учитывает продвижение частичное определение внутри `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="2595b-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="2595b-128">В результате он попытается скомпилировать два отдельных и различных класса, и именованные `sampleClass` , но с другой квалификации пути.</span><span class="sxs-lookup"><span data-stu-id="2595b-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="2595b-129">Компилятор объединяет частичные определения, только если их полные пути идентичны.</span><span class="sxs-lookup"><span data-stu-id="2595b-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="2595b-130">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="2595b-130">Recommendations</span></span>  
 <span data-ttu-id="2595b-131">Следующие рекомендации представляют хорошим стилем программирования.</span><span class="sxs-lookup"><span data-stu-id="2595b-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="2595b-132">**Уникальные имена.**</span><span class="sxs-lookup"><span data-stu-id="2595b-132">**Unique Names.**</span></span> <span data-ttu-id="2595b-133">Если у вас есть полный контроль над именованием элементов программирования, рекомендуется всегда использовать уникальные имена everywhere.</span><span class="sxs-lookup"><span data-stu-id="2595b-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="2595b-134">Идентичные имена требуют дополнительного уточнения и могут сделать код труднее читаться.</span><span class="sxs-lookup"><span data-stu-id="2595b-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="2595b-135">Они также могут привести к непредсказуемым результатам и неявных ошибок.</span><span class="sxs-lookup"><span data-stu-id="2595b-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="2595b-136">**Полное имя пространства имен.**</span><span class="sxs-lookup"><span data-stu-id="2595b-136">**Full Qualification.**</span></span> <span data-ttu-id="2595b-137">При работе с модулями и другие элементы в одном пространстве имен безопаснее использовать полное определение для всех элементов программирования.</span><span class="sxs-lookup"><span data-stu-id="2595b-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="2595b-138">Если повышение типа для члена модуля отменяется, не полностью уточнить этот член может случайно доступ к другому элементу программирования.</span><span class="sxs-lookup"><span data-stu-id="2595b-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2595b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2595b-139">See Also</span></span>  
 [<span data-ttu-id="2595b-140">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="2595b-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="2595b-141">Оператор Namespace</span><span class="sxs-lookup"><span data-stu-id="2595b-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="2595b-142">Partial</span><span class="sxs-lookup"><span data-stu-id="2595b-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="2595b-143">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2595b-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="2595b-144">Практическое руководство. Управление областью действия переменной</span><span class="sxs-lookup"><span data-stu-id="2595b-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="2595b-145">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="2595b-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
