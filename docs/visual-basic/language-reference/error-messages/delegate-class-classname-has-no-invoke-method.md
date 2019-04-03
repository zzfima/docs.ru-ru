---
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 463b4f50e8c431bbbc113509e5fd9dd1756b5928
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822522"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="85e60-102">Класс делегата\<имя_класса > "не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода</span><span class="sxs-lookup"><span data-stu-id="85e60-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="85e60-103">Вызов `Invoke` через делегат не выполнено, поскольку `Invoke` не реализован в классе делегата.</span><span class="sxs-lookup"><span data-stu-id="85e60-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="85e60-104">**Идентификатор ошибки:** BC30220</span><span class="sxs-lookup"><span data-stu-id="85e60-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85e60-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="85e60-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="85e60-106">Убедитесь, что создания экземпляра класса делегата с `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="85e60-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="85e60-107">Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.</span><span class="sxs-lookup"><span data-stu-id="85e60-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e60-108">См. также</span><span class="sxs-lookup"><span data-stu-id="85e60-108">See also</span></span>

- [<span data-ttu-id="85e60-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="85e60-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="85e60-110">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="85e60-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="85e60-111">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="85e60-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="85e60-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="85e60-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
