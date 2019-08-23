---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968359"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="c7036-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7036-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="c7036-103">Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="c7036-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="c7036-104">`ParamArray`может использоваться только в последнем параметре списка параметров.</span><span class="sxs-lookup"><span data-stu-id="c7036-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7036-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7036-105">Remarks</span></span>  
 <span data-ttu-id="c7036-106">`ParamArray`позволяет передавать процедуре произвольное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="c7036-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="c7036-107">Параметр всегда объявляется с помощью [ByVal.](../../../visual-basic/language-reference/modifiers/byval.md) `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="c7036-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="c7036-108">Можно указать один или несколько аргументов для `ParamArray` параметра, передав массив соответствующего типа данных, список значений с разделителями-запятыми или ничего вообще.</span><span class="sxs-lookup"><span data-stu-id="c7036-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="c7036-109">Дополнительные сведения см. в разделе «вызов ParamArray» в [массивах параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="c7036-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c7036-110">Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="c7036-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="c7036-111">Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="c7036-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="c7036-112">Модификатор `ParamArray` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="c7036-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c7036-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="c7036-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="c7036-114">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="c7036-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c7036-115">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="c7036-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c7036-116">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="c7036-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7036-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c7036-117">See also</span></span>

- [<span data-ttu-id="c7036-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c7036-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="c7036-119">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="c7036-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
