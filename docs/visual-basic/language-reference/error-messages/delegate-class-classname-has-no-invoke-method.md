---
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 3fe164d868ee7bde0e687e1d592f4d5a17565aea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803640"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="bd403-102">Класс делегата\<имя_класса > "не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода</span><span class="sxs-lookup"><span data-stu-id="bd403-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="bd403-103">Вызов `Invoke` через делегат не выполнено, поскольку `Invoke` не реализован в классе делегата.</span><span class="sxs-lookup"><span data-stu-id="bd403-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="bd403-104">**Идентификатор ошибки:** BC30220</span><span class="sxs-lookup"><span data-stu-id="bd403-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd403-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bd403-105">To correct this error</span></span>  
  
1. <span data-ttu-id="bd403-106">Убедитесь, что создания экземпляра класса делегата с `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="bd403-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="bd403-107">Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.</span><span class="sxs-lookup"><span data-stu-id="bd403-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd403-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bd403-108">See also</span></span>

- [<span data-ttu-id="bd403-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="bd403-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="bd403-110">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="bd403-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="bd403-111">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="bd403-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="bd403-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="bd403-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
