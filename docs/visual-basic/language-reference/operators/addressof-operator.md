---
title: "Оператор AddressOf (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e29b7ae2a6f6040cfc8c6e0cd0c9eb055a6694e9
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="4e74c-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e74c-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="4e74c-103">Создает экземпляр делегата процедуры, ссылающийся на указанную процедуру.</span><span class="sxs-lookup"><span data-stu-id="4e74c-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e74c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e74c-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="4e74c-105">Части</span><span class="sxs-lookup"><span data-stu-id="4e74c-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="4e74c-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4e74c-106">Required.</span></span> <span data-ttu-id="4e74c-107">Указывает процедуру, на которые ссылается созданный делегат процедуры.</span><span class="sxs-lookup"><span data-stu-id="4e74c-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e74c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e74c-108">Remarks</span></span>  
 <span data-ttu-id="4e74c-109">`AddressOf` Оператор создает делегат функции, который указывает функции, указанной `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="4e74c-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="4e74c-110">Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="4e74c-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="4e74c-111">Затем при вызове делегата функции вызывается указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4e74c-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="4e74c-112">`AddressOf` Оператор может использоваться как операнд конструктора делегата, или он может использоваться в контексте, в котором тип делегата можно определить с помощью компилятора.</span><span class="sxs-lookup"><span data-stu-id="4e74c-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e74c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4e74c-113">Example</span></span>  
 <span data-ttu-id="4e74c-114">В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` событие элемента управления button.</span><span class="sxs-lookup"><span data-stu-id="4e74c-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 <span data-ttu-id="4e74c-115">[!code-vb[VbVbalrDelegates №&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e74c-115">[!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e74c-116">Пример</span><span class="sxs-lookup"><span data-stu-id="4e74c-116">Example</span></span>  
 <span data-ttu-id="4e74c-117">В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="4e74c-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 <span data-ttu-id="4e74c-118">[!code-vb[VbVbalrDelegates №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e74c-118">[!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e74c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4e74c-119">See Also</span></span>  
 <span data-ttu-id="4e74c-120">[Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e74c-120">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="4e74c-121"> [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e74c-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="4e74c-122"> [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e74c-122"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="4e74c-123"> [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="4e74c-123"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>

