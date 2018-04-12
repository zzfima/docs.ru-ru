---
title: Оператор DirectCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="7670b-102">Оператор DirectCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7670b-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="7670b-103">Вводит операцию преобразования типа на основе наследования или реализации.</span><span class="sxs-lookup"><span data-stu-id="7670b-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7670b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="7670b-104">Remarks</span></span>  
 <span data-ttu-id="7670b-105">`DirectCast`не используйте в Visual Basic подпрограммы поддержки времени выполнения для преобразования, поэтому она обеспечивает немного лучшую производительность, чем `CType` при преобразовании из типа данных и `Object`.</span><span class="sxs-lookup"><span data-stu-id="7670b-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="7670b-106">Вы используете `DirectCast` аналогично тому, как использовать ключевое слово [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7670b-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="7670b-107">Можно указать выражение в качестве первого аргумента и тип для преобразования его в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="7670b-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="7670b-108">`DirectCast`требуется отношение наследования или реализации между типами данных обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="7670b-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="7670b-109">Это означает, что один тип должен реализовывать или наследовать из другого.</span><span class="sxs-lookup"><span data-stu-id="7670b-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="7670b-110">Ошибки и сбои</span><span class="sxs-lookup"><span data-stu-id="7670b-110">Errors and Failures</span></span>  
 <span data-ttu-id="7670b-111">`DirectCast`создает ошибку компилятора, если он обнаруживает, что существует отношение наследования или реализации.</span><span class="sxs-lookup"><span data-stu-id="7670b-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="7670b-112">Однако отсутствие ошибки компилятора не гарантирует успешное преобразование.</span><span class="sxs-lookup"><span data-stu-id="7670b-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="7670b-113">Если требуемое преобразование будет сужающим, то возможен сбой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7670b-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="7670b-114">В этом случае среда выполнения создает <xref:System.InvalidCastException> ошибки.</span><span class="sxs-lookup"><span data-stu-id="7670b-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="7670b-115">Ключевые слова преобразований</span><span class="sxs-lookup"><span data-stu-id="7670b-115">Conversion Keywords</span></span>  
 <span data-ttu-id="7670b-116">Сравнение ключевых слов преобразования типов выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7670b-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="7670b-117">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="7670b-117">Keyword</span></span>|<span data-ttu-id="7670b-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7670b-118">Data types</span></span>|<span data-ttu-id="7670b-119">Отношение аргументов</span><span class="sxs-lookup"><span data-stu-id="7670b-119">Argument relationship</span></span>|<span data-ttu-id="7670b-120">Ошибка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="7670b-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="7670b-121">Функция CType</span><span class="sxs-lookup"><span data-stu-id="7670b-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="7670b-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7670b-122">Any data types</span></span>|<span data-ttu-id="7670b-123">Должен быть определен расширяющее или сужающее преобразование между двумя типами данных</span><span class="sxs-lookup"><span data-stu-id="7670b-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="7670b-124">Создает исключение<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="7670b-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="7670b-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7670b-125">Any data types</span></span>|<span data-ttu-id="7670b-126">Один тип должен наследовать или реализовывать другой</span><span class="sxs-lookup"><span data-stu-id="7670b-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="7670b-127">Создает исключение<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="7670b-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="7670b-128">Оператор TryCast</span><span class="sxs-lookup"><span data-stu-id="7670b-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="7670b-129">Только ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="7670b-129">Reference types only</span></span>|<span data-ttu-id="7670b-130">Один тип должен наследовать или реализовывать другой</span><span class="sxs-lookup"><span data-stu-id="7670b-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="7670b-131">Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="7670b-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7670b-132">Пример</span><span class="sxs-lookup"><span data-stu-id="7670b-132">Example</span></span>  
 <span data-ttu-id="7670b-133">В следующем примере показано два способа использования `DirectCast`, завершается ошибкой во время выполнения и один, завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="7670b-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="7670b-134">В предыдущем примере тип времени выполнения `q` — `Double`.</span><span class="sxs-lookup"><span data-stu-id="7670b-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="7670b-135">`CType`завершается успешно, поскольку `Double` можно преобразовать в `Integer`.</span><span class="sxs-lookup"><span data-stu-id="7670b-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="7670b-136">Однако первый `DirectCast` завершается ошибкой во время выполнения, поскольку тип времени выполнения `Double` не имеет отношения наследования с `Integer`, даже если существует преобразование.</span><span class="sxs-lookup"><span data-stu-id="7670b-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="7670b-137">Второй `DirectCast` завершается успешно, поскольку он преобразует типа <xref:System.Windows.Forms.Form> ввода <xref:System.Windows.Forms.Control>, из которого <xref:System.Windows.Forms.Form> наследует.</span><span class="sxs-lookup"><span data-stu-id="7670b-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7670b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7670b-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7670b-139">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="7670b-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="7670b-140">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="7670b-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
