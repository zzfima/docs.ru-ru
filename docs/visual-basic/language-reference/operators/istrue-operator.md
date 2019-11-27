---
title: Оператор IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349514"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="d7986-102">Оператор IsTrue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7986-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="d7986-103">Определяет, является ли выражение `True`.</span><span class="sxs-lookup"><span data-stu-id="d7986-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="d7986-104">Нельзя явно вызывать `IsTrue` в коде, но компилятор Visual Basic может использовать его для создания кода на основе `OrElse`ных предложений.</span><span class="sxs-lookup"><span data-stu-id="d7986-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="d7986-105">Если вы определяете класс или структуру, а затем используете переменную этого типа в предложении `OrElse`, необходимо определить `IsTrue` для этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d7986-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="d7986-106">Компилятор рассматривает операторы `IsTrue` и `IsFalse` как *парную пару*.</span><span class="sxs-lookup"><span data-stu-id="d7986-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="d7986-107">Это означает, что при определении одного из них необходимо также определить другой.</span><span class="sxs-lookup"><span data-stu-id="d7986-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="d7986-108">Использование IsTrue компилятором</span><span class="sxs-lookup"><span data-stu-id="d7986-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="d7986-109">Определив класс или структуру, можно использовать переменную этого типа в операторе `For`, `If`, `Else If`или `While` или в предложении `When`.</span><span class="sxs-lookup"><span data-stu-id="d7986-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="d7986-110">В этом случае компилятору требуется оператор, преобразующий тип в `Boolean` значение, чтобы можно было проверить условие.</span><span class="sxs-lookup"><span data-stu-id="d7986-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="d7986-111">Он выполняет поиск подходящего оператора в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="d7986-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="d7986-112">Оператор расширяющего преобразования из класса или структуры для `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d7986-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="d7986-113">Оператор расширяющего преобразования из класса или структуры для `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="d7986-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="d7986-114">Оператор `IsTrue` в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="d7986-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="d7986-115">Суженное преобразование в `Boolean?`, которое не предусматривает преобразование из `Boolean` в `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="d7986-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="d7986-116">Оператор сужения преобразования из класса или структуры в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d7986-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="d7986-117">Если вы не определили преобразование в `Boolean` или оператор `IsTrue`, компилятор сигнализирует об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d7986-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7986-118">Оператор `IsTrue` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d7986-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="d7986-119">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="d7986-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d7986-120">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d7986-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7986-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d7986-121">Example</span></span>  
 <span data-ttu-id="d7986-122">В следующем примере кода определяется структура структуры, включающей определения для операторов `IsFalse` и `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="d7986-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="d7986-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d7986-123">See also</span></span>

- [<span data-ttu-id="d7986-124">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="d7986-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="d7986-125">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="d7986-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="d7986-126">Оператор OrElse</span><span class="sxs-lookup"><span data-stu-id="d7986-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
