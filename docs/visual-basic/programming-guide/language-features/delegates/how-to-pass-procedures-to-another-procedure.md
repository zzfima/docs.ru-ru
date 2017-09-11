---
title: "Практическое руководство: передача процедур другой процедуре в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 95cbcf836b0dad875851052a367666c00cd54e37
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="60cd9-102">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60cd9-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="60cd9-103">В этом примере демонстрируется использование делегатов для передачи процедуры другой процедуры.</span><span class="sxs-lookup"><span data-stu-id="60cd9-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="60cd9-104">Делегат — это тип, который можно использовать как любой другой тип в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="60cd9-104">A delegate is a type that you can use like any other type in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="60cd9-105">`AddressOf` Оператор возвращает объект делегата при применении к имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="60cd9-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="60cd9-106">В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с `AddressOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="60cd9-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="60cd9-107">Создание делегата и согласование процедур</span><span class="sxs-lookup"><span data-stu-id="60cd9-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="60cd9-108">Создать делегат с именем `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="60cd9-108">Create a delegate named `MathOperator`.</span></span>  
  
     <span data-ttu-id="60cd9-109">[!code-vb[VbVbalrDelegates&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="60cd9-109">[!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="60cd9-110">Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают `MathOperator`, то есть подписи совпадают.</span><span class="sxs-lookup"><span data-stu-id="60cd9-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     <span data-ttu-id="60cd9-111">[!code-vb[VbVbalrDelegates&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="60cd9-111">[!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span></span>  
  
3.  <span data-ttu-id="60cd9-112">Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="60cd9-112">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     <span data-ttu-id="60cd9-113">[!code-vb[VbVbalrDelegates&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="60cd9-113">[!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span></span>  
  
4.  <span data-ttu-id="60cd9-114">Создайте процедуру с именем `DelegateTest` , которая принимает делегат в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="60cd9-114">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="60cd9-115">Эта процедура может принимать ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуре соответствуют `MathOperator` подписи.</span><span class="sxs-lookup"><span data-stu-id="60cd9-115">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     <span data-ttu-id="60cd9-116">[!code-vb[VbVbalrDelegates&#4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="60cd9-116">[!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span></span>  
  
5.  <span data-ttu-id="60cd9-117">Создайте процедуру с именем `Test` , который вызывает `DelegateTest` с делегатом для `AddNumbers` как параметр и снова с делегатом для `SubtractNumbers` как параметр.</span><span class="sxs-lookup"><span data-stu-id="60cd9-117">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     <span data-ttu-id="60cd9-118">[!code-vb[VbVbalrDelegates&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="60cd9-118">[!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span></span>  
  
     <span data-ttu-id="60cd9-119">При `Test` является именем, то сначала он отображает результат `AddNumbers` на `5` и `3`, который равен 8.</span><span class="sxs-lookup"><span data-stu-id="60cd9-119">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="60cd9-120">Затем результат `SubtractNumbers` на `9` и `3` отображается, который равен 6.</span><span class="sxs-lookup"><span data-stu-id="60cd9-120">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cd9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="60cd9-121">See Also</span></span>  
 <span data-ttu-id="60cd9-122">[Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="60cd9-122">[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="60cd9-123"> [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="60cd9-123"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="60cd9-124"> [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="60cd9-124"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="60cd9-125"> [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="60cd9-125"> [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
