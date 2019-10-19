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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581818"
---
# <a name="goto-statement"></a><span data-ttu-id="25b63-102">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="25b63-102">GoTo Statement</span></span>
<span data-ttu-id="25b63-103">Безусловно подразделяется на указанную строку в процедуре.</span><span class="sxs-lookup"><span data-stu-id="25b63-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25b63-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="25b63-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="25b63-105">Part</span></span>  
 `line`  
 <span data-ttu-id="25b63-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="25b63-106">Required.</span></span> <span data-ttu-id="25b63-107">Метка любой линии.</span><span class="sxs-lookup"><span data-stu-id="25b63-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25b63-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="25b63-108">Remarks</span></span>  
 <span data-ttu-id="25b63-109">Оператор `GoTo` может создать ветвь только для строк в той процедуре, в которой она отображается.</span><span class="sxs-lookup"><span data-stu-id="25b63-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="25b63-110">Строка должна иметь метку, которая `GoTo` может ссылаться на.</span><span class="sxs-lookup"><span data-stu-id="25b63-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="25b63-111">Дополнительные сведения см. [в разделе инструкции. Метки](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="25b63-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25b63-112">`GoTo`ные инструкции могут усложнить чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="25b63-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="25b63-113">Везде, где это возможно, следует использовать структуру элементов управления.</span><span class="sxs-lookup"><span data-stu-id="25b63-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="25b63-114">Дополнительные сведения см. в разделе [поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="25b63-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="25b63-115">Нельзя использовать оператор `GoTo` для ветвления извне `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 или 2... 3ная конструкция к метке внутри.</span><span class="sxs-lookup"><span data-stu-id="25b63-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="25b63-116">Ветвление и конструкции try</span><span class="sxs-lookup"><span data-stu-id="25b63-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="25b63-117">В `Try`... `Catch`... `Finally`, для ветвления с помощью инструкции `GoTo` применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="25b63-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="25b63-118">Блок или область</span><span class="sxs-lookup"><span data-stu-id="25b63-118">Block or region</span></span>|<span data-ttu-id="25b63-119">Ветвление вне</span><span class="sxs-lookup"><span data-stu-id="25b63-119">Branching in from outside</span></span>|<span data-ttu-id="25b63-120">Ветвление из внутрь</span><span class="sxs-lookup"><span data-stu-id="25b63-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="25b63-121">блок `Try`</span><span class="sxs-lookup"><span data-stu-id="25b63-121">`Try` block</span></span>|<span data-ttu-id="25b63-122">Только из блока `Catch` той же конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25b63-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="25b63-123">Только за пределами всей конструкции</span><span class="sxs-lookup"><span data-stu-id="25b63-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="25b63-124">блок `Catch`</span><span class="sxs-lookup"><span data-stu-id="25b63-124">`Catch` block</span></span>|<span data-ttu-id="25b63-125">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="25b63-125">Never allowed</span></span>|<span data-ttu-id="25b63-126">Только за пределами всей конструкции или с блоком `Try` одной конструкции <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25b63-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="25b63-127">блок `Finally`</span><span class="sxs-lookup"><span data-stu-id="25b63-127">`Finally` block</span></span>|<span data-ttu-id="25b63-128">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="25b63-128">Never allowed</span></span>|<span data-ttu-id="25b63-129">Никогда не разрешено</span><span class="sxs-lookup"><span data-stu-id="25b63-129">Never allowed</span></span>|  
  
 <span data-ttu-id="25b63-130"><sup>1</sup> , если один `Try`... `Catch`... `Finally` конструкция вложена в другую, блок `Catch` может выполнить ветвление в блок `Try` на своем собственном уровне вложенности, но не в другой блок `Try`.</span><span class="sxs-lookup"><span data-stu-id="25b63-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="25b63-131">Вложенный `Try`... `Catch`... `Finally` конструкция должна полностью содержаться в `Try` или `Catch` блоке построения, внутри которого она вложена.</span><span class="sxs-lookup"><span data-stu-id="25b63-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="25b63-132">На следующем рисунке показана одна `Try`ная конструкция, вложенная в другую.</span><span class="sxs-lookup"><span data-stu-id="25b63-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="25b63-133">Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.</span><span class="sxs-lookup"><span data-stu-id="25b63-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="25b63-135">Пример</span><span class="sxs-lookup"><span data-stu-id="25b63-135">Example</span></span>  
 <span data-ttu-id="25b63-136">В следующем примере оператор `GoTo` используется для перехода к меткам линии в процедуре.</span><span class="sxs-lookup"><span data-stu-id="25b63-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="25b63-137">См. также</span><span class="sxs-lookup"><span data-stu-id="25b63-137">See also</span></span>

- [<span data-ttu-id="25b63-138">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="25b63-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="25b63-139">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="25b63-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="25b63-140">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="25b63-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="25b63-141">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="25b63-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="25b63-142">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="25b63-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="25b63-143">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="25b63-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="25b63-144">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="25b63-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="25b63-145">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="25b63-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
