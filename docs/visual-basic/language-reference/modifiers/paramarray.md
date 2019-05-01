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
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053916"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="61cda-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61cda-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="61cda-103">Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="61cda-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="61cda-104">`ParamArray` может использоваться только для последнего параметра в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="61cda-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cda-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="61cda-105">Remarks</span></span>  
 <span data-ttu-id="61cda-106">`ParamArray` позволяет передать произвольное число аргументов в процедуру.</span><span class="sxs-lookup"><span data-stu-id="61cda-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="61cda-107">Объект `ParamArray` параметр всегда объявляется с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="61cda-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="61cda-108">Можно указать один или несколько аргументов для `ParamArray` при передаче массива данных, соответствующий тип параметра, разделенный запятыми список значений, либо значение nothing вообще.</span><span class="sxs-lookup"><span data-stu-id="61cda-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="61cda-109">Дополнительные сведения см. в разделе «Вызов ParamArray» в [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="61cda-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="61cda-110">Каждый раз, когда вы имеете дело с массив, который может быть неограниченно большим, есть риск переполнения некоторой внутренней емкости приложения.</span><span class="sxs-lookup"><span data-stu-id="61cda-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="61cda-111">Если вы согласны с массивом параметров от вызывающего кода, следует проверить его длину и предпринять соответствующие действия, если она слишком велика для приложения.</span><span class="sxs-lookup"><span data-stu-id="61cda-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="61cda-112">Модификатор `ParamArray` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="61cda-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="61cda-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="61cda-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="61cda-114">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="61cda-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="61cda-115">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="61cda-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="61cda-116">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="61cda-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="61cda-117">См. также</span><span class="sxs-lookup"><span data-stu-id="61cda-117">See also</span></span>

- [<span data-ttu-id="61cda-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="61cda-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="61cda-119">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="61cda-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
