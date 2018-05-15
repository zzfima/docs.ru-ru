---
title: Оператор GoTo
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
ms.openlocfilehash: 27ebc677bab8b7f61a02408fddb30a6ec21c43cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="goto-statement"></a><span data-ttu-id="70c75-102">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="70c75-102">GoTo Statement</span></span>
<span data-ttu-id="70c75-103">Осуществляет безусловный переход на указанную строку в процедуре.</span><span class="sxs-lookup"><span data-stu-id="70c75-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70c75-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="70c75-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="70c75-105">Part</span></span>  
 `line`  
 <span data-ttu-id="70c75-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="70c75-106">Required.</span></span> <span data-ttu-id="70c75-107">Метка строки.</span><span class="sxs-lookup"><span data-stu-id="70c75-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70c75-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="70c75-108">Remarks</span></span>  
 <span data-ttu-id="70c75-109">`GoTo` Оператор может выполнять переход только к строкам в процедуре, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="70c75-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="70c75-110">Строка должна содержать строку, метка `GoTo` могут ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="70c75-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="70c75-111">Дополнительные сведения см. в разделе [как: метка инструкции](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="70c75-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70c75-112">`GoTo` операторы могут сделать код трудными для понимания и обслуживания.</span><span class="sxs-lookup"><span data-stu-id="70c75-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="70c75-113">По возможности используйте структуру управления.</span><span class="sxs-lookup"><span data-stu-id="70c75-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="70c75-114">Дополнительные сведения см. в разделе [поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="70c75-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="70c75-115">Нельзя использовать `GoTo` инструкции для выхода из блоков `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, или `Using`... `End Using` метку внутри этой конструкции.</span><span class="sxs-lookup"><span data-stu-id="70c75-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="70c75-116">Конструкции Try и ветвления</span><span class="sxs-lookup"><span data-stu-id="70c75-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="70c75-117">В рамках `Try`... `Catch`... `Finally` конструкция, применяются следующие правила для ветвления с `GoTo` инструкции.</span><span class="sxs-lookup"><span data-stu-id="70c75-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="70c75-118">Блок или область</span><span class="sxs-lookup"><span data-stu-id="70c75-118">Block or region</span></span>|<span data-ttu-id="70c75-119">Ветвление внутрь извне</span><span class="sxs-lookup"><span data-stu-id="70c75-119">Branching in from outside</span></span>|<span data-ttu-id="70c75-120">Ветвление вовне</span><span class="sxs-lookup"><span data-stu-id="70c75-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="70c75-121">`Try` Блок</span><span class="sxs-lookup"><span data-stu-id="70c75-121">`Try` block</span></span>|<span data-ttu-id="70c75-122">Только из `Catch` блок конструирование же <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70c75-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="70c75-123">Только вовне всей конструкции</span><span class="sxs-lookup"><span data-stu-id="70c75-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="70c75-124">`Catch` Блок</span><span class="sxs-lookup"><span data-stu-id="70c75-124">`Catch` block</span></span>|<span data-ttu-id="70c75-125">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="70c75-125">Never allowed</span></span>|<span data-ttu-id="70c75-126">Только вовне всей конструкции или `Try` блок конструирование же <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70c75-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="70c75-127">`Finally` Блок</span><span class="sxs-lookup"><span data-stu-id="70c75-127">`Finally` block</span></span>|<span data-ttu-id="70c75-128">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="70c75-128">Never allowed</span></span>|<span data-ttu-id="70c75-129">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="70c75-129">Never allowed</span></span>|  
  
 <span data-ttu-id="70c75-130"><sup>1</sup> Если один `Try`... `Catch`... `Finally` вложена в другую, `Catch` блок можно ветвление в `Try` блок в свой собственный уровень вложенности, но не в любой другой `Try` блока.</span><span class="sxs-lookup"><span data-stu-id="70c75-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="70c75-131">Вложенный `Try`... `Catch`... `Finally` конструкции, которые должны содержаться в полностью `Try` или `Catch` блок конструирование, в течение которого он является вложенным.</span><span class="sxs-lookup"><span data-stu-id="70c75-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="70c75-132">На следующем рисунке показано одно `Try` конструкции, вложенным в другой.</span><span class="sxs-lookup"><span data-stu-id="70c75-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="70c75-133">Различные ветви между блоками двух конструкций обозначены как допустимое или недопустимое.</span><span class="sxs-lookup"><span data-stu-id="70c75-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="70c75-134">![Графическая схема ветвления в конструкциях Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="70c75-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="70c75-135">Допустимые и недопустимые ветви в конструкциях Try</span><span class="sxs-lookup"><span data-stu-id="70c75-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="70c75-136">Пример</span><span class="sxs-lookup"><span data-stu-id="70c75-136">Example</span></span>  
 <span data-ttu-id="70c75-137">В следующем примере используется `GoTo` инструкции в ветвь на метки в процедуре.</span><span class="sxs-lookup"><span data-stu-id="70c75-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="70c75-138">См. также</span><span class="sxs-lookup"><span data-stu-id="70c75-138">See Also</span></span>  
 [<span data-ttu-id="70c75-139">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="70c75-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="70c75-140">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="70c75-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="70c75-141">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="70c75-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="70c75-142">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="70c75-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="70c75-143">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="70c75-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="70c75-144">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="70c75-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="70c75-145">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="70c75-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="70c75-146">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="70c75-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
