---
title: Копирование значения &#39;ByRef&#39; параметр &#39; &lt;имя_параметра&gt; &#39; обратно в соответствующий аргумент сводит тип &#39; &lt;Имя_типа1&gt; &#39; типу &#39; &lt;имя_типа2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18c72e56e4b2cc9c2251de2417a9f12a6688323f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="60da7-102">Копирование значения &#39;ByRef&#39; параметр &#39; &lt;имя_параметра&gt; &#39; обратно в соответствующий аргумент сводит тип &#39; &lt;Имя_типа1&gt; &#39; типу &#39; &lt;имя_типа2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="60da7-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="60da7-103">Процедура вызывается с аргументом, который расширяется до соответствующего параметра типа и сужающие преобразования из параметра к аргументу.</span><span class="sxs-lookup"><span data-stu-id="60da7-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="60da7-104">При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы.</span><span class="sxs-lookup"><span data-stu-id="60da7-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="60da7-105">Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="60da7-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="60da7-106">При использовании типа класса или структуры в вызове процедуры Visual Basic можно использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="60da7-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="60da7-107">Если передается аргумент [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.</span><span class="sxs-lookup"><span data-stu-id="60da7-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="60da7-108">В этом случае когда процедура возвращает результат, Visual Basic необходимо скопировать значение локальной переменной обратно в аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="60da7-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="60da7-109">Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется.</span><span class="sxs-lookup"><span data-stu-id="60da7-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="60da7-110">Но если типы различны, Visual Basic необходимо преобразовать в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="60da7-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="60da7-111">Если один из типов является типом соответствующего класса или структуры, объектов Visual Basic необходимо преобразовать его в и из другого типа.</span><span class="sxs-lookup"><span data-stu-id="60da7-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="60da7-112">Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.</span><span class="sxs-lookup"><span data-stu-id="60da7-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="60da7-113">**Идентификатор ошибки:** BC32053</span><span class="sxs-lookup"><span data-stu-id="60da7-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60da7-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="60da7-114">To correct this error</span></span>  
  
-   <span data-ttu-id="60da7-115">По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не нужно выполнять никаких преобразований.</span><span class="sxs-lookup"><span data-stu-id="60da7-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="60da7-116">Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не обязательно должны возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="60da7-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="60da7-117">Если требуется возвращать значение в аргумент вызова, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.</span><span class="sxs-lookup"><span data-stu-id="60da7-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60da7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="60da7-118">See Also</span></span>  
 [<span data-ttu-id="60da7-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="60da7-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="60da7-120">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="60da7-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="60da7-121">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="60da7-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="60da7-122">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="60da7-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="60da7-123">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="60da7-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="60da7-124">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="60da7-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="60da7-125">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="60da7-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="60da7-126">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60da7-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="60da7-127">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="60da7-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
