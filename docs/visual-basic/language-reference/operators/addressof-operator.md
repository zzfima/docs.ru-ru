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
ms.openlocfilehash: 2ebadf5ded1a23fe46b8e16cf18ae265b5d3c255
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591656"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="3e694-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e694-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="3e694-103">Создает экземпляр делегата, который ссылается на определенную процедуру.</span><span class="sxs-lookup"><span data-stu-id="3e694-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e694-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e694-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="3e694-105">Части</span><span class="sxs-lookup"><span data-stu-id="3e694-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="3e694-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3e694-106">Required.</span></span> <span data-ttu-id="3e694-107">Задает процедуру, на которую ссылается только что созданный делегат.</span><span class="sxs-lookup"><span data-stu-id="3e694-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e694-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e694-108">Remarks</span></span>  
 <span data-ttu-id="3e694-109">Оператор `AddressOf` создает делегат, указывающий на подпрограмму или функцию, заданную параметром `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="3e694-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="3e694-110">Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="3e694-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="3e694-111">Затем при вызове делегата вызывается указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3e694-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="3e694-112">Оператор `AddressOf` можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.</span><span class="sxs-lookup"><span data-stu-id="3e694-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e694-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3e694-113">Example</span></span>  
 <span data-ttu-id="3e694-114">В этом примере оператор `AddressOf` используется для обозначения делегата, обрабатывающего событие кнопки `Click`.</span><span class="sxs-lookup"><span data-stu-id="3e694-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="3e694-115">Пример</span><span class="sxs-lookup"><span data-stu-id="3e694-115">Example</span></span>  
 <span data-ttu-id="3e694-116">В следующем примере оператор `AddressOf` используется для обозначения функции запуска для потока.</span><span class="sxs-lookup"><span data-stu-id="3e694-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3e694-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3e694-117">See also</span></span>

- [<span data-ttu-id="3e694-118">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="3e694-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="3e694-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3e694-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3e694-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3e694-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3e694-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="3e694-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
