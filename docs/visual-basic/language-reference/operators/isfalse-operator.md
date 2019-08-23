---
title: Оператор IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917147"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="b0d91-102">Оператор IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0d91-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="b0d91-103">Определяет, является `False`ли выражение.</span><span class="sxs-lookup"><span data-stu-id="b0d91-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="b0d91-104">В коде нельзя `IsFalse` вызывать явным образом, но компилятор Visual Basic может использовать его для создания кода из `AndAlso` предложений.</span><span class="sxs-lookup"><span data-stu-id="b0d91-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="b0d91-105">Если вы определяете класс или структуру, а затем используете переменную этого типа в `AndAlso` предложении, необходимо определить `IsFalse` для этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b0d91-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="b0d91-106">Компилятор рассматривает `IsFalse` операторы и `IsTrue` как парную *пару*.</span><span class="sxs-lookup"><span data-stu-id="b0d91-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="b0d91-107">Это означает, что при определении одного из них необходимо также определить другой.</span><span class="sxs-lookup"><span data-stu-id="b0d91-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0d91-108">Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, если его операнд имеет тип этого класса или структуры. `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="b0d91-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b0d91-109">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="b0d91-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b0d91-110">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b0d91-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d91-111">Пример</span><span class="sxs-lookup"><span data-stu-id="b0d91-111">Example</span></span>  
 <span data-ttu-id="b0d91-112">В следующем примере кода определяется структура структуры, включающей определения для `IsFalse` операторов и. `IsTrue`</span><span class="sxs-lookup"><span data-stu-id="b0d91-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b0d91-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b0d91-113">See also</span></span>

- [<span data-ttu-id="b0d91-114">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="b0d91-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="b0d91-115">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="b0d91-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="b0d91-116">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="b0d91-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
