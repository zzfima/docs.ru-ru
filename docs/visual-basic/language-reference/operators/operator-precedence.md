---
title: "Порядок применения операторов в Visual Basic"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="f05aa-102">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f05aa-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="f05aa-103">Если несколько операций в выражении, каждая часть вычисляется и устранена в предопределенном порядке называется *приоритета операторов*.</span><span class="sxs-lookup"><span data-stu-id="f05aa-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="f05aa-104">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="f05aa-104">Precedence Rules</span></span>  
 <span data-ttu-id="f05aa-105">Если выражения содержат операторы с более чем одной категории, они вычисляются по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="f05aa-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="f05aa-106">Арифметические операторы и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и все имеют более высокий приоритет, чем сравнения, логические и битовые операторы.</span><span class="sxs-lookup"><span data-stu-id="f05aa-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="f05aa-107">Все операторы сравнения имеют одинаковый приоритет и все имеют более высокий приоритет, чем логические и битовые операторы, но более низкий приоритет, чем арифметических операторов и операторов объединения.</span><span class="sxs-lookup"><span data-stu-id="f05aa-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="f05aa-108">Логические и битовые операторы имеют порядок приоритета, описанный в следующем разделе, и имеют более низкий приоритет, чем арифметических операций, объединения и операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="f05aa-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="f05aa-109">Операторы с одинаковым приоритетом выполняются в порядке слева направо в том порядке, в котором они появляются в выражение.</span><span class="sxs-lookup"><span data-stu-id="f05aa-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="f05aa-110">Порядок приоритета</span><span class="sxs-lookup"><span data-stu-id="f05aa-110">Precedence Order</span></span>  
 <span data-ttu-id="f05aa-111">Операторы выполняются в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="f05aa-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="f05aa-112">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="f05aa-112">Await Operator</span></span>  
 <span data-ttu-id="f05aa-113">await</span><span class="sxs-lookup"><span data-stu-id="f05aa-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="f05aa-114">Арифметические операторы и операторы объединения</span><span class="sxs-lookup"><span data-stu-id="f05aa-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="f05aa-115">Возведение в степень (`^`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="f05aa-116">Унарный и минус (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="f05aa-117">Умножение и деление с плавающей запятой (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="f05aa-118">Целочисленное деление (`\`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="f05aa-119">Арифметический модуль (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="f05aa-120">Сложение и вычитание (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="f05aa-121">Объединение строк (`&`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="f05aa-122">Арифметический сдвиг разряда (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="f05aa-123">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="f05aa-123">Comparison Operators</span></span>  
 <span data-ttu-id="f05aa-124">Все операторы сравнения (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="f05aa-125">Логические и битовые операторы</span><span class="sxs-lookup"><span data-stu-id="f05aa-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="f05aa-126">Отрицание (`Not`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="f05aa-127">Умножение (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="f05aa-128">Дизъюнкции (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="f05aa-129">Исключающего логического сложения (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="f05aa-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="f05aa-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f05aa-130">Comments</span></span>  
 <span data-ttu-id="f05aa-131">`=` Оператор является только оператор сравнения на равенство, не оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="f05aa-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="f05aa-132">Оператор объединения строк (`&`) не является арифметический оператор, но в приоритете группируются с арифметическими операторами.</span><span class="sxs-lookup"><span data-stu-id="f05aa-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="f05aa-133">`Is` И `IsNot` операторы являются операторами сравнения ссылок объектов.</span><span class="sxs-lookup"><span data-stu-id="f05aa-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="f05aa-134">Они не выполняют сравнение значений двух объектов; они проверяют только определить, ссылаются ли две объектные переменные на один и тот же экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="f05aa-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="f05aa-135">Ассоциативность</span><span class="sxs-lookup"><span data-stu-id="f05aa-135">Associativity</span></span>  
 <span data-ttu-id="f05aa-136">Когда операторы с одинаковым приоритетом появляются вместе в выражении, например умножение и деление, компилятор вычисляет каждую операцию по порядку слева направо.</span><span class="sxs-lookup"><span data-stu-id="f05aa-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="f05aa-137">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f05aa-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="f05aa-138">Первое выражение вычисляется результат деления 96 / 8 (которая в результате дает 12), а затем деления 12 / 4, что в результате 3.</span><span class="sxs-lookup"><span data-stu-id="f05aa-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="f05aa-139">Так как компилятор вычисляет операции для `n1` слева направо, вычисление зависит от того, порядок явно указывается для `n2`.</span><span class="sxs-lookup"><span data-stu-id="f05aa-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="f05aa-140">Оба `n1` и `n2` имеют результат 3.</span><span class="sxs-lookup"><span data-stu-id="f05aa-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="f05aa-141">В отличие от этого `n3` имеет в результате 48, так как круглые скобки заставляют компилятор может вычислить 8 / 4 первого.</span><span class="sxs-lookup"><span data-stu-id="f05aa-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="f05aa-142">Из-за этого поведения, операторы, называются *левую ассоциативность* в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05aa-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="f05aa-143">Переопределение приоритет и ассоциативность операторов</span><span class="sxs-lookup"><span data-stu-id="f05aa-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="f05aa-144">Можно использовать скобки для принудительного выполнения некоторых частей выражения раньше других.</span><span class="sxs-lookup"><span data-stu-id="f05aa-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="f05aa-145">Это можно переопределить очередность и ассоциативность слева.</span><span class="sxs-lookup"><span data-stu-id="f05aa-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f05aa-146">всегда выполняет операции, заключенные в скобки, прежде чем за их пределами.</span><span class="sxs-lookup"><span data-stu-id="f05aa-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="f05aa-147">Тем не менее в скобки, это обеспечивает обычный приоритет и ассоциативность, если вы не используете круглые скобки в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="f05aa-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="f05aa-148">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f05aa-148">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f05aa-149">См. также</span><span class="sxs-lookup"><span data-stu-id="f05aa-149">See Also</span></span>  
 [<span data-ttu-id="f05aa-150">Оператор =</span><span class="sxs-lookup"><span data-stu-id="f05aa-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="f05aa-151">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="f05aa-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="f05aa-152">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="f05aa-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="f05aa-153">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="f05aa-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="f05aa-154">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="f05aa-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="f05aa-155">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="f05aa-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="f05aa-156">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f05aa-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="f05aa-157">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="f05aa-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
