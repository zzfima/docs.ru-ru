---
title: Приоритет операторов
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 318fcc3f35276ba0b2061ba9677c5fde29429f6f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348281"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="8dfa2-102">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dfa2-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="8dfa2-103">Если в выражении встречается несколько операций, каждая часть вычисляется и разрешается в заранее определенном порядке, который называется *приоритетом операторов*.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="8dfa2-104">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="8dfa2-104">Precedence Rules</span></span>
 <span data-ttu-id="8dfa2-105">Если выражения содержат операторы из более чем одной категории, они оцениваются в соответствии со следующими правилами.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="8dfa2-106">Арифметические и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и имеют более высокий приоритет, чем операторы сравнения, логического и побитового оператора.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="8dfa2-107">Все операторы сравнения имеют одинаковый приоритет, а все имеют более высокий приоритет, чем логические операторы and, но имеют более низкий приоритет, чем операторы арифметического и объединения.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="8dfa2-108">Логические и побитовые операторы имеют порядок приоритета, описанный в следующем разделе, и все имеют более низкий приоритет, чем арифметические операторы, операции объединения и сравнения.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="8dfa2-109">Операторы с одинаковым приоритетом вычисляются слева направо в том порядке, в котором они отображаются в выражении.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="8dfa2-110">Порядок очередности</span><span class="sxs-lookup"><span data-stu-id="8dfa2-110">Precedence Order</span></span>
 <span data-ttu-id="8dfa2-111">Операторы оцениваются в следующем порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="8dfa2-112">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="8dfa2-112">Await Operator</span></span>
 <span data-ttu-id="8dfa2-113">Ожидать</span><span class="sxs-lookup"><span data-stu-id="8dfa2-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="8dfa2-114">Арифметические и операторы объединения</span><span class="sxs-lookup"><span data-stu-id="8dfa2-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="8dfa2-115">Возведение в степень (`^`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="8dfa2-116">Унарное удостоверение и отрицание (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="8dfa2-117">Умножение и деление с плавающей запятой (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="8dfa2-118">Целочисленное деление (`\`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-118">Integer division (`\`)</span></span>

 <span data-ttu-id="8dfa2-119">Модульная арифметика (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="8dfa2-120">Сложение и вычитание (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="8dfa2-121">Объединение строк (`&`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="8dfa2-122">Арифметический сдвиг битов (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="8dfa2-123">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="8dfa2-123">Comparison Operators</span></span>
 <span data-ttu-id="8dfa2-124">Все операторы сравнения (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="8dfa2-125">Логические и побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="8dfa2-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="8dfa2-126">Отрицание (`Not`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-126">Negation (`Not`)</span></span>

 <span data-ttu-id="8dfa2-127">Умножение (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="8dfa2-128">Включающее сложение (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="8dfa2-129">Эксклюзивное сложение (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="8dfa2-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="8dfa2-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8dfa2-130">Comments</span></span>
 <span data-ttu-id="8dfa2-131">Оператор `=` является только оператором сравнения на равенство, а не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="8dfa2-132">Оператор объединения строк (`&`) не является арифметическим оператором, но в приоритете он сгруппирован с арифметическими операторами.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="8dfa2-133">Операторы `Is` и `IsNot` являются операторами сравнения ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="8dfa2-134">Они не сравнивают значения двух объектов; они только определяют, ссылаются ли две объектные переменные на один и тот же экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="8dfa2-135">ассоциативностью</span><span class="sxs-lookup"><span data-stu-id="8dfa2-135">Associativity</span></span>
 <span data-ttu-id="8dfa2-136">Если операторы с одинаковым приоритетом отображаются вместе в выражении, например умножение и деление, компилятор вычисляет каждую операцию в том виде, в котором она встретилась слева направо.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="8dfa2-137">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="8dfa2-138">Первое выражение вычисляет деление 96/8 (что приводит к 12), а затем деление на 12/4, что приводит к трем.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="8dfa2-139">Поскольку компилятор вычисляет операции для `n1` слева направо, вычисление будет таким же, когда порядок явно указывается для `n2`.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="8dfa2-140">И `n1`, и `n2` имеют результат 3.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="8dfa2-141">Напротив, `n3` имеет результат 48, поскольку круглые скобки заставляют компилятор сначала вычислить 8/4.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="8dfa2-142">Из-за такого поведения операторы говорят о том, что в Visual Basic не используется *ассоциативность* .</span><span class="sxs-lookup"><span data-stu-id="8dfa2-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="8dfa2-143">Переопределение приоритета и ассоциативности</span><span class="sxs-lookup"><span data-stu-id="8dfa2-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="8dfa2-144">Можно использовать круглые скобки, чтобы принудительно вычислить некоторые части выражения перед другими.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="8dfa2-145">Это может переопределять порядок приоритета и левую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="8dfa2-146">Visual Basic всегда выполняет операции, заключенные в круглые скобки, прежде чем они выходят за пределы.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="8dfa2-147">Однако в круглых скобках он поддерживает обычный приоритет и ассоциативность, если в круглых скобках не используются скобки.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="8dfa2-148">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-148">The following example illustrates this.</span></span>

```vb
Dim a, b, c, d, e, f, g As Double
a = 8.0
b = 3.0
c = 4.0
d = 2.0
e = 1.0
f = a - b + c / d * e
' The preceding line sets f to 7.0. Because of natural operator
' precedence and associativity, it is exactly equivalent to the
' following line.
f = (a - b) + ((c / d) * e)
' The following line overrides the natural operator precedence
' and left associativity.
g = (a - (b + c)) / (d * e)
' The preceding line sets g to 0.5.
```

## <a name="see-also"></a><span data-ttu-id="8dfa2-149">См. также</span><span class="sxs-lookup"><span data-stu-id="8dfa2-149">See also</span></span>

- [<span data-ttu-id="8dfa2-150">Оператор =</span><span class="sxs-lookup"><span data-stu-id="8dfa2-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="8dfa2-151">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="8dfa2-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="8dfa2-152">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="8dfa2-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="8dfa2-153">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="8dfa2-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="8dfa2-154">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="8dfa2-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="8dfa2-155">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="8dfa2-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="8dfa2-156">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="8dfa2-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8dfa2-157">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="8dfa2-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
