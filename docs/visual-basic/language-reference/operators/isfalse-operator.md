---
title: Оператор IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 85fd6b9264fa80c3636f2cb839c8fc5ed855ddc8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965661"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="bf377-102">Оператор IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf377-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="bf377-103">Определяет, является ли выражение `False`.</span><span class="sxs-lookup"><span data-stu-id="bf377-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="bf377-104">Нельзя вызывать `IsFalse` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `AndAlso` предложения.</span><span class="sxs-lookup"><span data-stu-id="bf377-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="bf377-105">Если вы задаете класса или структуры, а затем использовать переменную этого типа в `AndAlso` предложение, необходимо определить `IsFalse` для этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bf377-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="bf377-106">Компилятор считает, что `IsFalse` и `IsTrue` операторы как *соответствующую пару*.</span><span class="sxs-lookup"><span data-stu-id="bf377-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="bf377-107">Это означает, что если определить один из них, необходимо также определить другой.</span><span class="sxs-lookup"><span data-stu-id="bf377-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf377-108">`IsFalse` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bf377-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="bf377-109">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="bf377-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bf377-110">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bf377-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf377-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bf377-111">Example</span></span>  
 <span data-ttu-id="bf377-112">В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.</span><span class="sxs-lookup"><span data-stu-id="bf377-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="bf377-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bf377-113">See also</span></span>
- [<span data-ttu-id="bf377-114">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="bf377-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="bf377-115">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="bf377-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bf377-116">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="bf377-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
