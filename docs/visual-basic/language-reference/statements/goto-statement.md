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
ms.openlocfilehash: adb7668b6a818b2042a38f9458685a6f93085dc8
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332991"
---
# <a name="goto-statement"></a><span data-ttu-id="adcc1-102">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="adcc1-102">GoTo Statement</span></span>
<span data-ttu-id="adcc1-103">Осуществляет безусловный переход на указанную строку в процедуре.</span><span class="sxs-lookup"><span data-stu-id="adcc1-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcc1-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="adcc1-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="adcc1-105">Part</span></span>  
 `line`  
 <span data-ttu-id="adcc1-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="adcc1-106">Required.</span></span> <span data-ttu-id="adcc1-107">Метка строки.</span><span class="sxs-lookup"><span data-stu-id="adcc1-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adcc1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="adcc1-108">Remarks</span></span>  
 <span data-ttu-id="adcc1-109">`GoTo` Оператор может выполнять переход только к строкам в процедуре, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="adcc1-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="adcc1-110">Строка должна содержать строку, метка `GoTo` могут ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="adcc1-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="adcc1-111">Дополнительные сведения см. в разделе [как: метка инструкций](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="adcc1-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adcc1-112">`GoTo` операторы могут затруднить кода чтение и обслуживание.</span><span class="sxs-lookup"><span data-stu-id="adcc1-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="adcc1-113">По возможности используйте структуру управления.</span><span class="sxs-lookup"><span data-stu-id="adcc1-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="adcc1-114">Дополнительные сведения см. в разделе [поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="adcc1-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="adcc1-115">Нельзя использовать `GoTo` инструкции для выхода из блоков `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, или `Using`... `End Using` конструкции к метке внутри.</span><span class="sxs-lookup"><span data-stu-id="adcc1-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="adcc1-116">Конструкции Try и ветвления</span><span class="sxs-lookup"><span data-stu-id="adcc1-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="adcc1-117">В рамках `Try`... `Catch`... `Finally` конструкции, применяются следующие правила для ветвления с `GoTo` инструкции.</span><span class="sxs-lookup"><span data-stu-id="adcc1-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="adcc1-118">Блок или область</span><span class="sxs-lookup"><span data-stu-id="adcc1-118">Block or region</span></span>|<span data-ttu-id="adcc1-119">Ветвление внутрь извне</span><span class="sxs-lookup"><span data-stu-id="adcc1-119">Branching in from outside</span></span>|<span data-ttu-id="adcc1-120">Ветвление вовне</span><span class="sxs-lookup"><span data-stu-id="adcc1-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="adcc1-121">`Try` Блок</span><span class="sxs-lookup"><span data-stu-id="adcc1-121">`Try` block</span></span>|<span data-ttu-id="adcc1-122">Только из `Catch` блок используется одинаковая конструкция <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="adcc1-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="adcc1-123">Только за пределами всей конструкции</span><span class="sxs-lookup"><span data-stu-id="adcc1-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="adcc1-124">`Catch` Блок</span><span class="sxs-lookup"><span data-stu-id="adcc1-124">`Catch` block</span></span>|<span data-ttu-id="adcc1-125">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="adcc1-125">Never allowed</span></span>|<span data-ttu-id="adcc1-126">Только за пределами всей конструкции или `Try` блок используется одинаковая конструкция <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="adcc1-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="adcc1-127">`Finally` Блок</span><span class="sxs-lookup"><span data-stu-id="adcc1-127">`Finally` block</span></span>|<span data-ttu-id="adcc1-128">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="adcc1-128">Never allowed</span></span>|<span data-ttu-id="adcc1-129">Никогда не допускается</span><span class="sxs-lookup"><span data-stu-id="adcc1-129">Never allowed</span></span>|  
  
 <span data-ttu-id="adcc1-130"><sup>1</sup> Если один `Try`... `Catch`... `Finally` вложена в другую, `Catch` можно ветвь для блока `Try` блок в свой собственный уровень вложенности, но не в любых других `Try` блока.</span><span class="sxs-lookup"><span data-stu-id="adcc1-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="adcc1-131">Вложенный `Try`... `Catch`... `Finally` конструкции, которые должны содержаться в полностью `Try` или `Catch` блок конструкции, в который он вложен.</span><span class="sxs-lookup"><span data-stu-id="adcc1-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="adcc1-132">На следующем рисунке показан один `Try` конструкции, вложенным в другое.</span><span class="sxs-lookup"><span data-stu-id="adcc1-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="adcc1-133">Различные ветви между блоками двух конструкций обозначены как допустимое или недопустимое.</span><span class="sxs-lookup"><span data-stu-id="adcc1-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="adcc1-134">![Графическая схема ветвления в конструкциях Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="adcc1-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="adcc1-135">Допустимые и недопустимые ветви в конструкциях Try</span><span class="sxs-lookup"><span data-stu-id="adcc1-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="adcc1-136">Пример</span><span class="sxs-lookup"><span data-stu-id="adcc1-136">Example</span></span>  
 <span data-ttu-id="adcc1-137">В следующем примере используется `GoTo` инструкция ветви на метки в процедуре.</span><span class="sxs-lookup"><span data-stu-id="adcc1-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="adcc1-138">См. также</span><span class="sxs-lookup"><span data-stu-id="adcc1-138">See Also</span></span>  
 [<span data-ttu-id="adcc1-139">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="adcc1-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="adcc1-140">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="adcc1-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="adcc1-141">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="adcc1-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="adcc1-142">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="adcc1-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="adcc1-143">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="adcc1-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="adcc1-144">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="adcc1-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="adcc1-145">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="adcc1-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="adcc1-146">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="adcc1-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
