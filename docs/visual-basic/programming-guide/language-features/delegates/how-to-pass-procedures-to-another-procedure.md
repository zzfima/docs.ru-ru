---
title: Инструкции. Передача процедур в другую процедуру
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345248"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="18216-102">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18216-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="18216-103">В этом примере показано, как использовать делегаты для передачи процедуры в другую процедуру.</span><span class="sxs-lookup"><span data-stu-id="18216-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="18216-104">Делегат — это тип, который можно использовать как любой другой тип в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18216-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="18216-105">Оператор `AddressOf` возвращает объект делегата при применении к имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="18216-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="18216-106">Этот пример содержит процедуру с параметром делегата, который может принимать ссылку на другую процедуру, полученную с помощью оператора `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="18216-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="18216-107">Создание делегата и процедур сопоставления</span><span class="sxs-lookup"><span data-stu-id="18216-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="18216-108">Создайте делегат с именем `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="18216-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="18216-109">Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые соответствуют значениям `MathOperator`, чтобы сигнатуры совпадали.</span><span class="sxs-lookup"><span data-stu-id="18216-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="18216-110">Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="18216-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="18216-111">Создайте процедуру с именем `DelegateTest`, которая принимает делегат в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="18216-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="18216-112">Эта процедура может принять ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуры соответствуют подписи `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="18216-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="18216-113">Создайте процедуру с именем `Test`, которая вызывает `DelegateTest` один раз с делегатом для `AddNumbers` в качестве параметра и снова с делегатом для `SubtractNumbers` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="18216-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="18216-114">При вызове `Test` сначала отображается результат `AddNumbers`, действующего на `5` и `3`, что равно 8.</span><span class="sxs-lookup"><span data-stu-id="18216-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="18216-115">Затем отображается результат `SubtractNumbers`, действующего в `9` и `3`, что равно 6.</span><span class="sxs-lookup"><span data-stu-id="18216-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18216-116">См. также</span><span class="sxs-lookup"><span data-stu-id="18216-116">See also</span></span>

- [<span data-ttu-id="18216-117">Делегаты</span><span class="sxs-lookup"><span data-stu-id="18216-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="18216-118">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="18216-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="18216-119">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="18216-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="18216-120">Практическое руководство. Вызов метода делегата</span><span class="sxs-lookup"><span data-stu-id="18216-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
