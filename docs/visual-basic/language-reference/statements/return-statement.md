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
ms.openlocfilehash: edaaf09f5a984344f7e89c9da988c529774934e9
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583258"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="edda7-102">Оператор Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edda7-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="edda7-103">Возвращает управление коду, который вызвал процедуру `Function`, `Sub`, `Get`, `Set` или `Operator`.</span><span class="sxs-lookup"><span data-stu-id="edda7-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edda7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edda7-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="edda7-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="edda7-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="edda7-106">Требуется в `Function`, `Get` или процедуре `Operator`.</span><span class="sxs-lookup"><span data-stu-id="edda7-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="edda7-107">Выражение, представляющее значение, возвращаемое вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="edda7-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edda7-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="edda7-108">Remarks</span></span>  
 <span data-ttu-id="edda7-109">В `Sub` или `Set` инструкция `Return` эквивалентна инструкции `Exit Sub` или `Exit Property`, а `expression` не должен быть указан.</span><span class="sxs-lookup"><span data-stu-id="edda7-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="edda7-110">В `Function`, `Get` или `Operator` инструкция `Return` должна включать `expression`, а `expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры.</span><span class="sxs-lookup"><span data-stu-id="edda7-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="edda7-111">В `Function` или `Get` можно также назначить выражение для имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить инструкцию `Exit Function` или `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="edda7-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="edda7-112">В `Operator` процедуре необходимо использовать `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="edda7-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="edda7-113">В той же процедуре можно включить столько `Return` инструкций, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="edda7-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edda7-114">Код в блоке `Finally` выполняется после того, как обнаруживается инструкция `Return` в блоке `Try` или `Catch`, но перед выполнением этой инструкции `Return`.</span><span class="sxs-lookup"><span data-stu-id="edda7-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="edda7-115">Инструкция `Return` не может быть включена в блок `Finally`.</span><span class="sxs-lookup"><span data-stu-id="edda7-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edda7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="edda7-116">Example</span></span>  
 <span data-ttu-id="edda7-117">В следующем примере оператор `Return` используется несколько раз для возврата к вызывающему коду, если процедура не должна выполнять никаких других действий.</span><span class="sxs-lookup"><span data-stu-id="edda7-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="edda7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="edda7-118">See also</span></span>

- [<span data-ttu-id="edda7-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="edda7-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="edda7-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="edda7-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="edda7-121">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="edda7-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="edda7-122">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="edda7-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="edda7-123">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="edda7-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="edda7-124">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="edda7-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="edda7-125">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="edda7-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="edda7-126">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="edda7-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
