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
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760374"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="2d545-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d545-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="2d545-103">Создает экземпляр делегата, который ссылается на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="2d545-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d545-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d545-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="2d545-105">Части</span><span class="sxs-lookup"><span data-stu-id="2d545-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="2d545-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2d545-106">Required.</span></span> <span data-ttu-id="2d545-107">Указывает процедуру, на которые ссылается вновь созданного делегата.</span><span class="sxs-lookup"><span data-stu-id="2d545-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d545-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d545-108">Remarks</span></span>  
 <span data-ttu-id="2d545-109">`AddressOf` Оператор создает делегат, указывающий sub или function, определяемое `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="2d545-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="2d545-110">Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="2d545-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="2d545-111">Затем при вызове делегата вызывает указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2d545-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="2d545-112">`AddressOf` Оператор может использоваться в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.</span><span class="sxs-lookup"><span data-stu-id="2d545-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d545-113">Пример</span><span class="sxs-lookup"><span data-stu-id="2d545-113">Example</span></span>  
 <span data-ttu-id="2d545-114">В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="2d545-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="2d545-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2d545-115">Example</span></span>  
 <span data-ttu-id="2d545-116">В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="2d545-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="2d545-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2d545-117">See also</span></span>

- [<span data-ttu-id="2d545-118">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="2d545-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="2d545-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="2d545-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="2d545-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="2d545-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2d545-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="2d545-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
