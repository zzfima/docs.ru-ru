---
title: Порядок применения операторов в Visual Basic
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
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830036"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="fbc21-102">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbc21-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="fbc21-103">Если в выражении несколько операций, каждая часть вычисляется и разрешить в заранее определенном порядке вызывается *порядок применения операторов*.</span><span class="sxs-lookup"><span data-stu-id="fbc21-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="fbc21-104">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="fbc21-104">Precedence Rules</span></span>  
 <span data-ttu-id="fbc21-105">Если выражения содержат операторы из более чем одной категории, они вычисляются по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="fbc21-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="fbc21-106">Арифметические операторы и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и все имеют более высокий приоритет, чем сравнения, логические и побитовые операторы.</span><span class="sxs-lookup"><span data-stu-id="fbc21-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="fbc21-107">Все операторы сравнения имеют равный приоритет и более высокий приоритет, чем логические и побитовые операторы, но более низкий приоритет, чем арифметические операторы и операторы объединения.</span><span class="sxs-lookup"><span data-stu-id="fbc21-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="fbc21-108">Логические и побитовые операторы имеют порядок приоритета, описанный в следующем разделе, и все имеют более низкий приоритет, чем арифметические операции, объединения и операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="fbc21-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="fbc21-109">Операторы с одинаковым приоритетом выполняются в порядке слева направо в порядке, в котором они появляются в выражении.</span><span class="sxs-lookup"><span data-stu-id="fbc21-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="fbc21-110">Порядок приоритета</span><span class="sxs-lookup"><span data-stu-id="fbc21-110">Precedence Order</span></span>  
 <span data-ttu-id="fbc21-111">Операторы выполняются в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="fbc21-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="fbc21-112">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="fbc21-112">Await Operator</span></span>  
 <span data-ttu-id="fbc21-113">Await</span><span class="sxs-lookup"><span data-stu-id="fbc21-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="fbc21-114">Арифметические и операторы объединения</span><span class="sxs-lookup"><span data-stu-id="fbc21-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="fbc21-115">Возведение в степень (`^`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="fbc21-116">Унарный и минус (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="fbc21-117">Умножение и деление с плавающей запятой (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="fbc21-118">Целочисленное деление (`\`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="fbc21-119">Арифметический модуль (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="fbc21-120">Сложение и вычитание (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="fbc21-121">Объединение строк (`&`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="fbc21-122">Сдвиг битов арифметические (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="fbc21-123">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="fbc21-123">Comparison Operators</span></span>  
 <span data-ttu-id="fbc21-124">Все операторы сравнения (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="fbc21-125">Логические и побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="fbc21-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="fbc21-126">Отрицание (`Not`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="fbc21-127">Совместно (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="fbc21-128">Дизъюнкции (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="fbc21-129">Исключающего логического сложения (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="fbc21-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="fbc21-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fbc21-130">Comments</span></span>  
 <span data-ttu-id="fbc21-131">`=` Оператор имеет только оператор сравнения на равенство, не оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="fbc21-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="fbc21-132">Оператор объединения строк (`&`) не является арифметический оператор, но в приоритете группируется с арифметическими операторами.</span><span class="sxs-lookup"><span data-stu-id="fbc21-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="fbc21-133">`Is` И `IsNot` операторы, операторы сравнения объекта ссылки.</span><span class="sxs-lookup"><span data-stu-id="fbc21-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="fbc21-134">Они не выполняют сравнение значений двух объектов; они проверяют только определить, ссылаются ли две объектные переменные на один и тот же экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="fbc21-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="fbc21-135">Ассоциативность</span><span class="sxs-lookup"><span data-stu-id="fbc21-135">Associativity</span></span>  
 <span data-ttu-id="fbc21-136">Когда операторы с одинаковым приоритетом появляются вместе в выражении, например, умножение и деление, компилятор вычисляет каждую операцию по порядку слева направо.</span><span class="sxs-lookup"><span data-stu-id="fbc21-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="fbc21-137">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fbc21-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="fbc21-138">Для первого выражения деления 96 / 8 (что приводит к 12), а затем деления 12 / 4, что приводит к трем.</span><span class="sxs-lookup"><span data-stu-id="fbc21-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="fbc21-139">Так как компилятор вычисляет операции для `n1` слева направо, вычисление зависит от того, порядок явно указывается для `n2`.</span><span class="sxs-lookup"><span data-stu-id="fbc21-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="fbc21-140">Оба `n1` и `n2` имеют результат 3.</span><span class="sxs-lookup"><span data-stu-id="fbc21-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="fbc21-141">Напротив `n3` имеет результат 48, так как круглые скобки заставляют компилятор может вычислить 8 / 4 первый.</span><span class="sxs-lookup"><span data-stu-id="fbc21-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="fbc21-142">Из-за этого поведения, операторы, называются *левую ассоциативность* в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fbc21-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="fbc21-143">Переопределение приоритет и ассоциативность операторов</span><span class="sxs-lookup"><span data-stu-id="fbc21-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="fbc21-144">Можно использовать скобки для принудительного выполнения некоторых частей выражения раньше других.</span><span class="sxs-lookup"><span data-stu-id="fbc21-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="fbc21-145">Это можно переопределить очередность и ассоциативность слева.</span><span class="sxs-lookup"><span data-stu-id="fbc21-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="fbc21-146">Visual Basic всегда выполняет операции, которые заключаются в скобки, прежде чем за их пределами.</span><span class="sxs-lookup"><span data-stu-id="fbc21-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="fbc21-147">Тем не менее в скобки, он поддерживает обычный приоритет и ассоциативность операторов, если вы не используете круглые скобки в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="fbc21-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="fbc21-148">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fbc21-148">The following example illustrates this.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="fbc21-149">См. также</span><span class="sxs-lookup"><span data-stu-id="fbc21-149">See also</span></span>

- [<span data-ttu-id="fbc21-150">Оператор =</span><span class="sxs-lookup"><span data-stu-id="fbc21-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="fbc21-151">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="fbc21-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="fbc21-152">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="fbc21-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="fbc21-153">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="fbc21-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="fbc21-154">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="fbc21-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="fbc21-155">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="fbc21-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="fbc21-156">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="fbc21-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fbc21-157">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="fbc21-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
