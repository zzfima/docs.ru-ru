---
title: Практическое руководство. Передача процедур другой процедуре в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30264e0480b603b21f8f71893af0fd742af40286
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="835dd-102">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="835dd-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="835dd-103">В этом примере показано, как использование делегатов для передачи процедуры другой процедуры.</span><span class="sxs-lookup"><span data-stu-id="835dd-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="835dd-104">Делегат — это тип, который можно использовать как любой другой тип в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="835dd-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="835dd-105">`AddressOf` Оператор возвращает объект делегата при применении к имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="835dd-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="835dd-106">В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с `AddressOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="835dd-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="835dd-107">Создание делегата и согласование процедур</span><span class="sxs-lookup"><span data-stu-id="835dd-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="835dd-108">Создать делегат с именем `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="835dd-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="835dd-109">Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают `MathOperator`, после чего подписи совпадают.</span><span class="sxs-lookup"><span data-stu-id="835dd-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="835dd-110">Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="835dd-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="835dd-111">Создайте процедуру с именем `DelegateTest` , который принимает делегат в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="835dd-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="835dd-112">Эта процедура может принимать ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуры совпадают `MathOperator` подписи.</span><span class="sxs-lookup"><span data-stu-id="835dd-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="835dd-113">Создайте процедуру с именем `Test` , который вызывает `DelegateTest` с делегатом для `AddNumbers` как параметр и снова с делегатом для `SubtractNumbers` как параметр.</span><span class="sxs-lookup"><span data-stu-id="835dd-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="835dd-114">При `Test` — вызывается, то сначала он отображает результат `AddNumbers` на `5` и `3`, который равен 8.</span><span class="sxs-lookup"><span data-stu-id="835dd-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="835dd-115">Затем результат `SubtractNumbers` действует для `9` и `3` отображается, который равен 6.</span><span class="sxs-lookup"><span data-stu-id="835dd-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835dd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="835dd-116">See Also</span></span>  
 [<span data-ttu-id="835dd-117">Делегаты</span><span class="sxs-lookup"><span data-stu-id="835dd-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="835dd-118">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="835dd-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="835dd-119">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="835dd-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="835dd-120">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="835dd-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
