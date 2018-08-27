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
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932596"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="f0e53-102">Оператор Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0e53-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="f0e53-103">Возвращает элемент управления в код, который вызвал `Function`, `Sub`, `Get`, `Set`, или `Operator` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f0e53-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0e53-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="f0e53-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="f0e53-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="f0e53-106">Требуется в `Function`, `Get`, или `Operator` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f0e53-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="f0e53-107">Выражение, представляющее значение, возвращаемое вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="f0e53-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e53-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0e53-108">Remarks</span></span>  
 <span data-ttu-id="f0e53-109">В `Sub` или `Set` процедуре `Return` оператор эквивалентен `Exit Sub` или `Exit Property` инструкции, и `expression` не следует указывать.</span><span class="sxs-lookup"><span data-stu-id="f0e53-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="f0e53-110">В `Function`, `Get`, или `Operator` процедуре `Return` инструкция должна включать `expression`, и `expression` должны иметь тип данных, которое можно преобразовать в тип возвращаемого значения процедуры.</span><span class="sxs-lookup"><span data-stu-id="f0e53-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="f0e53-111">В `Function` или `Get` процедуры, также существует возможность назначения выражения имени процедуры для использования в качестве возвращаемого значения и последующее выполнение `Exit Function` или `Exit Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f0e53-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="f0e53-112">В `Operator` процедуру, необходимо использовать `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="f0e53-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="f0e53-113">Можно включить столько `Return` инструкций в той же процедуре соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f0e53-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0e53-114">Код в `Finally` блок выполняется после `Return` инструкции в `Try` или `Catch` блок обнаружен, но до этого `Return` выполняет инструкцию.</span><span class="sxs-lookup"><span data-stu-id="f0e53-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="f0e53-115">Объект `Return` инструкции не могут быть включены в `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="f0e53-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0e53-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f0e53-116">Example</span></span>  
 <span data-ttu-id="f0e53-117">В следующем примере используется `Return` инструкции несколько раз, чтобы вернуться к вызывающему коду, если процедуру не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="f0e53-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f0e53-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f0e53-118">See Also</span></span>  
 [<span data-ttu-id="f0e53-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f0e53-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="f0e53-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f0e53-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="f0e53-121">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="f0e53-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="f0e53-122">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="f0e53-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="f0e53-123">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="f0e53-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="f0e53-124">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f0e53-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="f0e53-125">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="f0e53-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="f0e53-126">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="f0e53-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
