---
title: Оператор Return (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957677"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="e8e8a-102">Оператор Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8e8a-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="e8e8a-103">Возвращает управление `Function`коду, который вызвал процедуру `Get`, `Sub`,, `Set`или `Operator` .</span><span class="sxs-lookup"><span data-stu-id="e8e8a-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8e8a-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="e8e8a-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="e8e8a-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="e8e8a-106">Требуется в `Function`процедуре, `Get`или. `Operator`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="e8e8a-107">Выражение, представляющее значение, возвращаемое вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="e8e8a-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8e8a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8e8a-108">Remarks</span></span>  
 <span data-ttu-id="e8e8a-109">`Set` `Exit Property` В процедуре `Sub` `Exit Sub` или инструкция эквивалентна оператору или и`expression` не должна быть указана. `Return`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="e8e8a-110">`Get` Впроцедуре`Return` ,или`expression`инструкция должна включать оператор и`expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры. `Operator` `Function`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="e8e8a-111">В процедуре `Get` `Exit Function` или вы также можете назначить выражение имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить инструкцию или `Exit Property`. `Function`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="e8e8a-112">В процедуре необходимо использовать `Return expression`. `Operator`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="e8e8a-113">В одной процедуре можно включить `Return` столько инструкций, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="e8e8a-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8e8a-114">Код `Finally` в блоке выполняется `Try` `Return` после обнаружения оператора в блоке или `Catch` , но перед выполнением этой `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e8e8a-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="e8e8a-115">Инструкция не может быть включена `Finally` в блок. `Return`</span><span class="sxs-lookup"><span data-stu-id="e8e8a-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8e8a-116">Пример</span><span class="sxs-lookup"><span data-stu-id="e8e8a-116">Example</span></span>  
 <span data-ttu-id="e8e8a-117">В следующем примере `Return` оператор используется несколько раз для возврата к вызывающему коду, если процедура не должна предпринимать никаких других действий.</span><span class="sxs-lookup"><span data-stu-id="e8e8a-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="e8e8a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e8e8a-118">See also</span></span>

- [<span data-ttu-id="e8e8a-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="e8e8a-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e8e8a-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="e8e8a-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e8e8a-121">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="e8e8a-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="e8e8a-122">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="e8e8a-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="e8e8a-123">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="e8e8a-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="e8e8a-124">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="e8e8a-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="e8e8a-125">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="e8e8a-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="e8e8a-126">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e8e8a-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
