---
title: Неявное преобразование из &#39; &lt;Имя_типа1&gt; &#39; для &#39; &lt;имя_типа2&gt; &#39; при копировании значения &#39;ByRef&#39; параметр &#39; &lt; имя_параметра&gt; &#39; обратно в соответствующий аргумент.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86a618206bcfd932e41410e80c12bc166a3f67f3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="6182e-102">Неявное преобразование из &#39; &lt;Имя_типа1&gt; &#39; для &#39; &lt;имя_типа2&gt; &#39; при копировании значения &#39;ByRef&#39; параметр &#39; &lt; имя_параметра&gt; &#39; обратно в соответствующий аргумент.</span><span class="sxs-lookup"><span data-stu-id="6182e-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="6182e-103">Процедура вызывается с [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) аргумент типа, отличного от соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="6182e-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="6182e-104">Если передается аргумент `ByRef`, Visual Basic иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.</span><span class="sxs-lookup"><span data-stu-id="6182e-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="6182e-105">В этом случае когда процедура возвращает результат, Visual Basic необходимо скопировать значение локальной переменной обратно в аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="6182e-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="6182e-106">Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется.</span><span class="sxs-lookup"><span data-stu-id="6182e-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="6182e-107">Но если типы различны, Visual Basic необходимо преобразовать в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="6182e-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="6182e-108">Так как нельзя использовать `CType` или любые другие преобразования ключевые слова в аргумент процедуры или параметра, такое преобразование всегда является неявным.</span><span class="sxs-lookup"><span data-stu-id="6182e-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="6182e-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="6182e-109">By default, this message is a warning.</span></span> <span data-ttu-id="6182e-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6182e-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6182e-111">**Идентификатор ошибки:** BC41999</span><span class="sxs-lookup"><span data-stu-id="6182e-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6182e-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6182e-112">To correct this error</span></span>  
  
-   <span data-ttu-id="6182e-113">По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не нужно выполнять никаких преобразований.</span><span class="sxs-lookup"><span data-stu-id="6182e-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="6182e-114">Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не обязательно должны возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="6182e-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6182e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6182e-115">See Also</span></span>  
 [<span data-ttu-id="6182e-116">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6182e-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="6182e-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="6182e-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="6182e-118">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="6182e-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="6182e-119">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="6182e-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
