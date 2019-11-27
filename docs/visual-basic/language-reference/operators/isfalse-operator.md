---
title: Оператор IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349518"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="40ffa-102">Оператор IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40ffa-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="40ffa-103">Определяет, является ли выражение `False`.</span><span class="sxs-lookup"><span data-stu-id="40ffa-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="40ffa-104">Нельзя явно вызывать `IsFalse` в коде, но компилятор Visual Basic может использовать его для создания кода на основе `AndAlso`ных предложений.</span><span class="sxs-lookup"><span data-stu-id="40ffa-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="40ffa-105">Если вы определяете класс или структуру, а затем используете переменную этого типа в предложении `AndAlso`, необходимо определить `IsFalse` для этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="40ffa-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="40ffa-106">Компилятор рассматривает операторы `IsFalse` и `IsTrue` как *парную пару*.</span><span class="sxs-lookup"><span data-stu-id="40ffa-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="40ffa-107">Это означает, что при определении одного из них необходимо также определить другой.</span><span class="sxs-lookup"><span data-stu-id="40ffa-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40ffa-108">Оператор `IsFalse` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="40ffa-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="40ffa-109">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="40ffa-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="40ffa-110">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40ffa-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40ffa-111">Пример</span><span class="sxs-lookup"><span data-stu-id="40ffa-111">Example</span></span>  
 <span data-ttu-id="40ffa-112">В следующем примере кода определяется структура структуры, включающей определения для операторов `IsFalse` и `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="40ffa-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="40ffa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="40ffa-113">See also</span></span>

- [<span data-ttu-id="40ffa-114">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="40ffa-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="40ffa-115">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="40ffa-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="40ffa-116">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="40ffa-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
