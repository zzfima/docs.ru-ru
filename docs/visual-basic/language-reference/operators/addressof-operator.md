---
title: Оператор AddressOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="f1c0b-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1c0b-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="f1c0b-103">Создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1c0b-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="f1c0b-105">Части</span><span class="sxs-lookup"><span data-stu-id="f1c0b-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="f1c0b-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-106">Required.</span></span> <span data-ttu-id="f1c0b-107">Указывает процедуру, на которые ссылается созданный делегат процедуры.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1c0b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1c0b-108">Remarks</span></span>  
 <span data-ttu-id="f1c0b-109">`AddressOf` Оператор создает делегат функции, который указывает функции, указанной `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="f1c0b-110">Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="f1c0b-111">Затем при вызове функции вызывается указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="f1c0b-112">`AddressOf` Оператор можно использовать в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1c0b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f1c0b-113">Example</span></span>  
 <span data-ttu-id="f1c0b-114">В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="f1c0b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="f1c0b-115">Example</span></span>  
 <span data-ttu-id="f1c0b-116">В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="f1c0b-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f1c0b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f1c0b-117">See Also</span></span>  
 [<span data-ttu-id="f1c0b-118">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="f1c0b-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="f1c0b-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f1c0b-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="f1c0b-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f1c0b-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="f1c0b-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f1c0b-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
