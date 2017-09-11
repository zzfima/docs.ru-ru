---
title: "При копировании значения параметра «ByRef» &quot;&lt;parametername&gt;«обратно в соответствующий аргумент сводит тип»&lt;typename1&gt;«к типу»&lt;typename2&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
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
ms.openlocfilehash: 10ad4af689c11f3e4defe43c4fed9ed579ba5305
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="ff9e6-102">При копировании значения параметра «ByRef» "&lt;parametername&gt;«обратно в соответствующий аргумент сводит тип»&lt;typename1&gt;«к типу»&lt;typename2&gt;"</span><span class="sxs-lookup"><span data-stu-id="ff9e6-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="ff9e6-103">Процедура вызывается с аргументом, который может быть расширен до соответствующего типа параметра и сужающее преобразование параметра к аргументу.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="ff9e6-104">При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="ff9e6-105">Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="ff9e6-106">При использовании типов класса или структуры в вызове процедуры [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] можно использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="ff9e6-107">При передаче аргумента [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="ff9e6-108">В случае, когда процедура возвращает результат [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен скопировать значение локальной переменной обратно в аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="ff9e6-109">Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="ff9e6-110">Но если типы различны, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо преобразовать в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-110">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="ff9e6-111">Если один из типов является типом соответствующего класса или структуры, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо преобразовать его в и из другого типа.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="ff9e6-112">Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="ff9e6-113">**Идентификатор ошибки:** BC32053</span><span class="sxs-lookup"><span data-stu-id="ff9e6-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff9e6-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ff9e6-114">To correct this error</span></span>  
  
-   <span data-ttu-id="ff9e6-115">По возможности используйте аргумент вызова того же типа, что и параметр процедуры так [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не нужно выполнять никаких преобразований.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="ff9e6-116">Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр для [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="ff9e6-117">Если требуется возвращать значение в аргументе, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.</span><span class="sxs-lookup"><span data-stu-id="ff9e6-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9e6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ff9e6-118">See Also</span></span>  
 <span data-ttu-id="ff9e6-119">[Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-119">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="ff9e6-120"> [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-120"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="ff9e6-121"> [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-121"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="ff9e6-122"> [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-122"> [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span></span>  
<span data-ttu-id="ff9e6-123"> [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-123"> [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="ff9e6-124"> [Практическое руководство: определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-124"> [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="ff9e6-125"> [Практическое руководство: определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-125"> [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="ff9e6-126"> [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ff9e6-126"> [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ff9e6-127"> [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="ff9e6-127"> [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
