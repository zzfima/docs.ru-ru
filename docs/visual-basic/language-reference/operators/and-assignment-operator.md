---
title: Оператор &amp; = (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 82d791e5d66c301442c99d2cc73e3172c3e30f17
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591628"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="cd147-102">Оператор &amp; = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd147-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="cd147-103">Сцепляет выражение `String` к переменной или свойству `String` и присваивает результат переменной или свойству.</span><span class="sxs-lookup"><span data-stu-id="cd147-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd147-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd147-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="cd147-105">Части</span><span class="sxs-lookup"><span data-stu-id="cd147-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="cd147-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cd147-106">Required.</span></span> <span data-ttu-id="cd147-107">Любая переменная или свойство `String`.</span><span class="sxs-lookup"><span data-stu-id="cd147-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="cd147-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cd147-108">Required.</span></span> <span data-ttu-id="cd147-109">Произвольное выражение `String` .</span><span class="sxs-lookup"><span data-stu-id="cd147-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd147-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd147-110">Remarks</span></span>  
 <span data-ttu-id="cd147-111">Элемент в левой части оператора `&=` может быть простой скалярной переменной, свойством или элементом массива.</span><span class="sxs-lookup"><span data-stu-id="cd147-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="cd147-112">Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="cd147-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="cd147-113">Оператор `&=` объединяет выражение `String` непосредственно с переменной или свойством `String` слева и присваивает результат переменной или свойству слева.</span><span class="sxs-lookup"><span data-stu-id="cd147-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="cd147-114">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="cd147-114">Overloading</span></span>  
 <span data-ttu-id="cd147-115">[Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="cd147-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cd147-116">Перегрузка оператора `&` влияет на поведение оператора `&=`.</span><span class="sxs-lookup"><span data-stu-id="cd147-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="cd147-117">Если в коде используется `&=` для класса или структуры, которая перегружает `&`, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="cd147-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cd147-118">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="cd147-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd147-119">Пример</span><span class="sxs-lookup"><span data-stu-id="cd147-119">Example</span></span>  
 <span data-ttu-id="cd147-120">В следующем примере оператор `&=` используется для сцепления двух переменных `String` и присваивания результата первой переменной.</span><span class="sxs-lookup"><span data-stu-id="cd147-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cd147-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cd147-121">See also</span></span>

- [<span data-ttu-id="cd147-122">Оператор &</span><span class="sxs-lookup"><span data-stu-id="cd147-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="cd147-123">Оператор +=</span><span class="sxs-lookup"><span data-stu-id="cd147-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="cd147-124">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="cd147-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="cd147-125">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="cd147-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="cd147-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd147-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cd147-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="cd147-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="cd147-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="cd147-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
