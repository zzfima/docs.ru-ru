---
title: Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588834"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="95bf6-102">Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода</span><span class="sxs-lookup"><span data-stu-id="95bf6-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="95bf6-103">Вызов `Invoke` в делегате не выполнено, поскольку `Invoke` не реализован в классе делегата.</span><span class="sxs-lookup"><span data-stu-id="95bf6-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="95bf6-104">**Идентификатор ошибки:** BC30220</span><span class="sxs-lookup"><span data-stu-id="95bf6-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95bf6-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="95bf6-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="95bf6-106">Убедитесь, что экземпляр класса делегата был создан с `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="95bf6-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="95bf6-107">Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.</span><span class="sxs-lookup"><span data-stu-id="95bf6-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bf6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="95bf6-108">See Also</span></span>  
 [<span data-ttu-id="95bf6-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="95bf6-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="95bf6-110">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="95bf6-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="95bf6-111">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="95bf6-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="95bf6-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="95bf6-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
