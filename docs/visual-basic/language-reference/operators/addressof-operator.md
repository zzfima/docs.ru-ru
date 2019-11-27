---
title: Оператор AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: e88520bd7e731a35b98c1d40c5210dc5d1314911
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350279"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="fbef5-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbef5-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="fbef5-103">Создает экземпляр делегата, который ссылается на определенную процедуру.</span><span class="sxs-lookup"><span data-stu-id="fbef5-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbef5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbef5-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="fbef5-105">Части</span><span class="sxs-lookup"><span data-stu-id="fbef5-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="fbef5-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="fbef5-106">Required.</span></span> <span data-ttu-id="fbef5-107">Задает процедуру, на которую ссылается только что созданный делегат.</span><span class="sxs-lookup"><span data-stu-id="fbef5-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbef5-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="fbef5-108">Remarks</span></span>  
 <span data-ttu-id="fbef5-109">Оператор `AddressOf` создает делегат, указывающий на подпрограмму или функцию, указанную в `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="fbef5-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="fbef5-110">Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="fbef5-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="fbef5-111">Затем при вызове делегата вызывается указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fbef5-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="fbef5-112">Оператор `AddressOf` можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.</span><span class="sxs-lookup"><span data-stu-id="fbef5-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbef5-113">Пример</span><span class="sxs-lookup"><span data-stu-id="fbef5-113">Example</span></span>  
 <span data-ttu-id="fbef5-114">В этом примере оператор `AddressOf` используется для обозначения делегата, обрабатывающего событие `Click` кнопки.</span><span class="sxs-lookup"><span data-stu-id="fbef5-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="fbef5-115">Пример</span><span class="sxs-lookup"><span data-stu-id="fbef5-115">Example</span></span>  
 <span data-ttu-id="fbef5-116">В следующем примере оператор `AddressOf` используется для обозначения функции запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="fbef5-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="fbef5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fbef5-117">See also</span></span>

- [<span data-ttu-id="fbef5-118">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="fbef5-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="fbef5-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="fbef5-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="fbef5-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="fbef5-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="fbef5-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="fbef5-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
