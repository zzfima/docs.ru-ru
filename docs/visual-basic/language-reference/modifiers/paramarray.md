---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="bbb88-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbb88-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="bbb88-103">Указывает, что параметр процедуры принимает необязательный массив элементов заданного типа.</span><span class="sxs-lookup"><span data-stu-id="bbb88-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="bbb88-104">`ParamArray`может использоваться только для последнего параметра из списка параметров.</span><span class="sxs-lookup"><span data-stu-id="bbb88-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbb88-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbb88-105">Remarks</span></span>  
 <span data-ttu-id="bbb88-106">`ParamArray`позволяет передать произвольное число аргументов в процедуру.</span><span class="sxs-lookup"><span data-stu-id="bbb88-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="bbb88-107">Объект `ParamArray` всегда параметр объявлен с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="bbb88-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="bbb88-108">Можно указать один или несколько аргументов для `ParamArray` параметра при передаче массива соответствующие данные типа, список разделенных запятыми значений или nothing вообще.</span><span class="sxs-lookup"><span data-stu-id="bbb88-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="bbb88-109">Дополнительные сведения см. в разделе «Вызов ParamArray» в [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bbb88-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bbb88-110">При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="bbb88-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="bbb88-111">Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие действия, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="bbb88-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="bbb88-112">Модификатор `ParamArray` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="bbb88-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bbb88-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="bbb88-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="bbb88-114">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bbb88-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bbb88-115">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="bbb88-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bbb88-116">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="bbb88-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bbb88-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb88-117">See Also</span></span>  
 [<span data-ttu-id="bbb88-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="bbb88-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="bbb88-119">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="bbb88-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
