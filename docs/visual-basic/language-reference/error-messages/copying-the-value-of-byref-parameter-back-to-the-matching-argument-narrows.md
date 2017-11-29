---
title: "Копирование значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент сужает от типа &#39;&lt; Имя_типа1&gt;&#39; ввода &#39;&lt; имя_типа2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords: BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="54bdc-102">Копирование значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент сужает от типа &#39;&lt; Имя_типа1&gt;&#39; ввода &#39;&lt; имя_типа2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="54bdc-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="54bdc-103">Процедура вызывается с аргументом, который расширяется до соответствующего параметра типа и сужающие преобразования из параметра к аргументу.</span><span class="sxs-lookup"><span data-stu-id="54bdc-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="54bdc-104">При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы.</span><span class="sxs-lookup"><span data-stu-id="54bdc-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="54bdc-105">Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="54bdc-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="54bdc-106">При использовании типа класса или структуры в вызове процедуры [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] может использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="54bdc-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="54bdc-107">Если передается аргумент [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.</span><span class="sxs-lookup"><span data-stu-id="54bdc-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="54bdc-108">В случае когда процедура возвращает результат, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна скопировать значение локальной переменной обратно в аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54bdc-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="54bdc-109">Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется.</span><span class="sxs-lookup"><span data-stu-id="54bdc-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="54bdc-110">Но если типы различны, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна выполнить преобразование в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="54bdc-110">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="54bdc-111">Если один из типов является типом соответствующего класса или структуры, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна преобразовать его в другой тип и из него.</span><span class="sxs-lookup"><span data-stu-id="54bdc-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="54bdc-112">Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.</span><span class="sxs-lookup"><span data-stu-id="54bdc-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="54bdc-113">**Идентификатор ошибки:** BC32053</span><span class="sxs-lookup"><span data-stu-id="54bdc-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54bdc-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="54bdc-114">To correct this error</span></span>  
  
-   <span data-ttu-id="54bdc-115">По возможности используйте аргумент вызова того же типа, что и параметр процедуры, чтобы среде [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не нужно было выполнять никаких преобразований.</span><span class="sxs-lookup"><span data-stu-id="54bdc-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="54bdc-116">Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не обязательно должны возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="54bdc-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="54bdc-117">Если требуется возвращать значение в аргумент вызова, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.</span><span class="sxs-lookup"><span data-stu-id="54bdc-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bdc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="54bdc-118">See Also</span></span>  
 [<span data-ttu-id="54bdc-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="54bdc-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="54bdc-120">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="54bdc-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="54bdc-121">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="54bdc-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="54bdc-122">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="54bdc-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="54bdc-123">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="54bdc-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="54bdc-124">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="54bdc-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="54bdc-125">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="54bdc-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="54bdc-126">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54bdc-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="54bdc-127">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="54bdc-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
