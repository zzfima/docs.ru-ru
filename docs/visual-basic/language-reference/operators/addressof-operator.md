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
ms.openlocfilehash: 9d8515b6d5b0caf3552ed05a7e0cd4a271efaf54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830348"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="bf685-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf685-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="bf685-103">Создает экземпляр делегата процедуры, который ссылается на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="bf685-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf685-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf685-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="bf685-105">Части</span><span class="sxs-lookup"><span data-stu-id="bf685-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="bf685-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="bf685-106">Required.</span></span> <span data-ttu-id="bf685-107">Указывает процедуру, на которые ссылается созданный делегат процедуры.</span><span class="sxs-lookup"><span data-stu-id="bf685-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf685-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf685-108">Remarks</span></span>  
 <span data-ttu-id="bf685-109">`AddressOf` Оператор создает делегат функции, который указывает на функцию, указанную аргументом `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="bf685-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="bf685-110">Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="bf685-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="bf685-111">Затем при вызове делегата функция вызывает указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bf685-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="bf685-112">`AddressOf` Оператор может использоваться в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.</span><span class="sxs-lookup"><span data-stu-id="bf685-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf685-113">Пример</span><span class="sxs-lookup"><span data-stu-id="bf685-113">Example</span></span>  
 <span data-ttu-id="bf685-114">В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="bf685-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="bf685-115">Пример</span><span class="sxs-lookup"><span data-stu-id="bf685-115">Example</span></span>  
 <span data-ttu-id="bf685-116">В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="bf685-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="bf685-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bf685-117">See also</span></span>

- [<span data-ttu-id="bf685-118">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="bf685-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="bf685-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bf685-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="bf685-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="bf685-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="bf685-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="bf685-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
