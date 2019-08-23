---
title: '- Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: eb34b34986613f36b624c43c04f98390ffba4fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965867"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="f702c-102">Оператор - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f702c-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="f702c-103">Возвращает разность между двумя числовыми выражениями или отрицательным значением числового выражения.</span><span class="sxs-lookup"><span data-stu-id="f702c-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f702c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f702c-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="f702c-105">Части</span><span class="sxs-lookup"><span data-stu-id="f702c-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="f702c-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f702c-106">Required.</span></span> <span data-ttu-id="f702c-107">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f702c-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f702c-108">Требуется, `–` если оператор не вычисляет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="f702c-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="f702c-109">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f702c-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="f702c-110">Результат</span><span class="sxs-lookup"><span data-stu-id="f702c-110">Result</span></span>  
 <span data-ttu-id="f702c-111">Результатом является разница между `expression1` и `expression2`или отрицательным значением `expression1`.</span><span class="sxs-lookup"><span data-stu-id="f702c-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="f702c-112">Тип данных result является числовым типом, подходящим для типов `expression1` данных и. `expression2`</span><span class="sxs-lookup"><span data-stu-id="f702c-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f702c-113">См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="f702c-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f702c-114">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="f702c-114">Supported Types</span></span>  
 <span data-ttu-id="f702c-115">все числовые типы.</span><span class="sxs-lookup"><span data-stu-id="f702c-115">All numeric types.</span></span> <span data-ttu-id="f702c-116">К ним относятся типы без знака и тип с плавающей запятой `Decimal`и.</span><span class="sxs-lookup"><span data-stu-id="f702c-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f702c-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f702c-117">Remarks</span></span>  
 <span data-ttu-id="f702c-118">При первом использовании, показанном в приведенном выше синтаксисе `–` , оператор является *бинарным* арифметическим оператором вычитания для разности двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="f702c-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="f702c-119">Во втором описании синтаксиса, показанного ранее, `–` оператор является *унарным* оператором отрицания для отрицательного значения выражения.</span><span class="sxs-lookup"><span data-stu-id="f702c-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="f702c-120">В этом смысле отрицание состоит в обратном знаке `expression1` , чтобы результат был положительным, если `expression1` является отрицательным.</span><span class="sxs-lookup"><span data-stu-id="f702c-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="f702c-121">Если любое из выражений имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), `–` оператор обрабатывает его как ноль.</span><span class="sxs-lookup"><span data-stu-id="f702c-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f702c-122">Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `–`</span><span class="sxs-lookup"><span data-stu-id="f702c-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f702c-123">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="f702c-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="f702c-124">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f702c-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f702c-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f702c-125">Example</span></span>  
 <span data-ttu-id="f702c-126">В следующем примере `–` оператор используется для вычисления и возврата разницы между двумя числами, а затем для отрицания числа.</span><span class="sxs-lookup"><span data-stu-id="f702c-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="f702c-127">После выполнения этих инструкций `binaryResult` содержит 124,45 и `unaryResult` содержит – 334,90.</span><span class="sxs-lookup"><span data-stu-id="f702c-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f702c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f702c-128">See also</span></span>

- [<span data-ttu-id="f702c-129">Оператор-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f702c-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="f702c-130">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="f702c-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f702c-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f702c-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f702c-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f702c-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f702c-133">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f702c-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
