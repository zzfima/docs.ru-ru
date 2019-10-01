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
ms.openlocfilehash: 5f6b6b67e2999d380cfca078a43162b3e1db2206
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701304"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="d857c-102">Оператор - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d857c-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="d857c-103">Возвращает разность между двумя числовыми выражениями или отрицательным значением числового выражения.</span><span class="sxs-lookup"><span data-stu-id="d857c-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d857c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d857c-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="d857c-105">или</span><span class="sxs-lookup"><span data-stu-id="d857c-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="d857c-106">Части</span><span class="sxs-lookup"><span data-stu-id="d857c-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="d857c-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d857c-107">Required.</span></span> <span data-ttu-id="d857c-108">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d857c-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d857c-109">Требуется, если оператор `–` не вычисляет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="d857c-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="d857c-110">Произвольное числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d857c-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="d857c-111">Результат</span><span class="sxs-lookup"><span data-stu-id="d857c-111">Result</span></span>  
 <span data-ttu-id="d857c-112">Результатом является разница между `expression1` и `expression2` или отрицательным значением `expression1`.</span><span class="sxs-lookup"><span data-stu-id="d857c-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="d857c-113">Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="d857c-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="d857c-114">См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="d857c-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="d857c-115">Поддерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="d857c-115">Supported Types</span></span>  
 <span data-ttu-id="d857c-116">все числовые типы.</span><span class="sxs-lookup"><span data-stu-id="d857c-116">All numeric types.</span></span> <span data-ttu-id="d857c-117">К ним относятся типы без знака и тип с плавающей запятой `Decimal`и.</span><span class="sxs-lookup"><span data-stu-id="d857c-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d857c-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="d857c-118">Remarks</span></span>  
 <span data-ttu-id="d857c-119">При первом использовании, показанном в приведенном выше синтаксисе, оператор `–` является *бинарным* арифметическим оператором вычитания для разности двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="d857c-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="d857c-120">Во втором описании синтаксиса, показанного ранее, оператор `–` является *унарным* оператором отрицания для отрицательного значения выражения.</span><span class="sxs-lookup"><span data-stu-id="d857c-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="d857c-121">В этом смысле отрицание состоит из обратного знака `expression1`, чтобы результат был положительным, если `expression1` имеет отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="d857c-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="d857c-122">Если любое из выражений имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оператор `–` обрабатывает его как ноль.</span><span class="sxs-lookup"><span data-stu-id="d857c-122">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d857c-123">Оператор `–` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d857c-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d857c-124">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="d857c-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="d857c-125">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d857c-125">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d857c-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d857c-126">Example</span></span>  
 <span data-ttu-id="d857c-127">В следующем примере оператор `–` используется для вычисления и возврата разницы между двумя числами, а затем для отрицания числа.</span><span class="sxs-lookup"><span data-stu-id="d857c-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="d857c-128">После выполнения этих инструкций `binaryResult` содержит 124,45, а `unaryResult` содержит – 334,90.</span><span class="sxs-lookup"><span data-stu-id="d857c-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d857c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d857c-129">See also</span></span>

- [<span data-ttu-id="d857c-130">Оператор-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d857c-130">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="d857c-131">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="d857c-131">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="d857c-132">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d857c-132">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d857c-133">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d857c-133">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d857c-134">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d857c-134">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
