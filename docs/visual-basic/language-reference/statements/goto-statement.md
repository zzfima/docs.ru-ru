---
title: Оператор GoTo (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912452"
---
# <a name="goto-statement"></a><span data-ttu-id="9e498-102">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="9e498-102">GoTo Statement</span></span>
<span data-ttu-id="9e498-103">Безусловно подразделяется на указанную строку в процедуре.</span><span class="sxs-lookup"><span data-stu-id="9e498-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e498-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e498-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="9e498-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="9e498-105">Part</span></span>  
 `line`  
 <span data-ttu-id="9e498-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e498-106">Required.</span></span> <span data-ttu-id="9e498-107">Метка любой линии.</span><span class="sxs-lookup"><span data-stu-id="9e498-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e498-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e498-108">Remarks</span></span>  
 <span data-ttu-id="9e498-109">`GoTo` Оператор может создать ветвь только для строк в процедуре, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="9e498-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="9e498-110">Строка должна иметь метку, которая `GoTo` может ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="9e498-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="9e498-111">Дополнительные сведения см. в разделе [Практическое руководство. Операторы](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)меток.</span><span class="sxs-lookup"><span data-stu-id="9e498-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e498-112">`GoTo`инструкции могут усложнить чтение и поддержку кода.</span><span class="sxs-lookup"><span data-stu-id="9e498-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="9e498-113">Везде, где это возможно, следует использовать структуру элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9e498-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="9e498-114">Дополнительные сведения см. в разделе [Поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="9e498-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="9e498-115">Нельзя использовать `GoTo` оператор для ветвления `For`извне... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With` или`Using`... `End Using` для создания метки в.</span><span class="sxs-lookup"><span data-stu-id="9e498-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="9e498-116">Ветвление и конструкции try</span><span class="sxs-lookup"><span data-stu-id="9e498-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="9e498-117">`Try`В... `Catch`... для создания ветвления `GoTo` с помощью оператора применяются следующие правила. `Finally`</span><span class="sxs-lookup"><span data-stu-id="9e498-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="9e498-118">Блок или область</span><span class="sxs-lookup"><span data-stu-id="9e498-118">Block or region</span></span>|<span data-ttu-id="9e498-119">Ветвление вне</span><span class="sxs-lookup"><span data-stu-id="9e498-119">Branching in from outside</span></span>|<span data-ttu-id="9e498-120">Ветвление из внутрь</span><span class="sxs-lookup"><span data-stu-id="9e498-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="9e498-121">`Try`блок</span><span class="sxs-lookup"><span data-stu-id="9e498-121">`Try` block</span></span>|<span data-ttu-id="9e498-122">Только из `Catch` блока одной конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9e498-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="9e498-123">Только за пределами всей конструкции</span><span class="sxs-lookup"><span data-stu-id="9e498-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="9e498-124">`Catch`блок</span><span class="sxs-lookup"><span data-stu-id="9e498-124">`Catch` block</span></span>|<span data-ttu-id="9e498-125">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="9e498-125">Never allowed</span></span>|<span data-ttu-id="9e498-126">Только за пределами всей конструкции или с `Try` блоком той же конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9e498-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="9e498-127">`Finally`блок</span><span class="sxs-lookup"><span data-stu-id="9e498-127">`Finally` block</span></span>|<span data-ttu-id="9e498-128">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="9e498-128">Never allowed</span></span>|<span data-ttu-id="9e498-129">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="9e498-129">Never allowed</span></span>|  
  
 <span data-ttu-id="9e498-130"><sup>1</sup> , если `Try`один... `Catch`... Конструкция вложена в другую `Catch` , `Try` блок может выполнять ветвление в блок на своем собственном уровне вложенности, но не в другой `Try` блок. `Finally`</span><span class="sxs-lookup"><span data-stu-id="9e498-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="9e498-131">Вложенный `Try`... `Catch`... конструкция должна полностью содержаться `Try` в блоке или `Catch` конструкции, внутри которой она вложена. `Finally`</span><span class="sxs-lookup"><span data-stu-id="9e498-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="9e498-132">На следующем рисунке показана `Try` одна конструкция, вложенная в другую.</span><span class="sxs-lookup"><span data-stu-id="9e498-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="9e498-133">Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.</span><span class="sxs-lookup"><span data-stu-id="9e498-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="9e498-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9e498-135">Example</span></span>  
 <span data-ttu-id="9e498-136">В следующем примере `GoTo` оператор используется для перехода к меткам линии в процедуре.</span><span class="sxs-lookup"><span data-stu-id="9e498-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="9e498-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9e498-137">See also</span></span>

- [<span data-ttu-id="9e498-138">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="9e498-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="9e498-139">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="9e498-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="9e498-140">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="9e498-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="9e498-141">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="9e498-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="9e498-142">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="9e498-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="9e498-143">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="9e498-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="9e498-144">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="9e498-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="9e498-145">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="9e498-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
