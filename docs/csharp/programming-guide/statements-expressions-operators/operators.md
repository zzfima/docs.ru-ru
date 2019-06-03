---
title: Руководство по программированию на C#. Операторы
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 60e7f7c25b525c6db856731bd16c1c0e60efe6d6
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422925"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="eea90-102">Операторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="eea90-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="eea90-103">В языке C# *оператор* — это элемент программы, который применяется для одного или нескольких *операндов* в выражении или инструкции.</span><span class="sxs-lookup"><span data-stu-id="eea90-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="eea90-104">Операторы, в которых используется один операнд, например оператор инкремента (`++`) или `new`, называются *унарными* .</span><span class="sxs-lookup"><span data-stu-id="eea90-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="eea90-105">Операторы, в которых используются два операнда, например арифметические операторы (`+`,`-`,`*`,`/`), называются *бинарными* .</span><span class="sxs-lookup"><span data-stu-id="eea90-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="eea90-106">Для одного оператора — условного (`?:`) — используются три операнда, и такой оператор является единственным троичным оператором в C#.</span><span class="sxs-lookup"><span data-stu-id="eea90-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="eea90-107">Следующая строка кода C# содержит один унарный оператор и еще один операнд.</span><span class="sxs-lookup"><span data-stu-id="eea90-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="eea90-108">Оператор инкремента `++`изменяет значение операнда `y`.</span><span class="sxs-lookup"><span data-stu-id="eea90-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="eea90-109">Следующая строка кода C# содержит два бинарных оператора с двумя операндами в каждом.</span><span class="sxs-lookup"><span data-stu-id="eea90-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="eea90-110">Оператор присваивания `=`содержит в качестве операндов целочисленную переменную `y` и выражение `2 + 3` .</span><span class="sxs-lookup"><span data-stu-id="eea90-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="eea90-111">Выражение `2 + 3` состоит из оператора сложения и двух операндов — `2` и `3`.</span><span class="sxs-lookup"><span data-stu-id="eea90-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="eea90-112">Операнд может быть допустимым выражением, представляющим собой код любой длины, а также может содержать любое число вложенных выражений.</span><span class="sxs-lookup"><span data-stu-id="eea90-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="eea90-113">В выражении, содержащем несколько операторов, порядок применения операторов определяется *приоритетом операторов*, *ассоциативностью* и скобками.</span><span class="sxs-lookup"><span data-stu-id="eea90-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="eea90-114">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="eea90-114">Operator precedence</span></span>
  
<span data-ttu-id="eea90-115">Каждый оператор имеет определенный приоритет.</span><span class="sxs-lookup"><span data-stu-id="eea90-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="eea90-116">В выражении, содержащем несколько операторов с разными уровнями приоритета, порядок вычисления операторов определяется их приоритетом.</span><span class="sxs-lookup"><span data-stu-id="eea90-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="eea90-117">Например, следующий оператор назначает 3 в `n1`:</span><span class="sxs-lookup"><span data-stu-id="eea90-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="eea90-118">Сначала выполняется умножение, так как оно имеет приоритет над вычитанием.</span><span class="sxs-lookup"><span data-stu-id="eea90-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="eea90-119">Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](../../language-reference/operators/index.md).</span><span class="sxs-lookup"><span data-stu-id="eea90-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="eea90-120">Ассоциативность</span><span class="sxs-lookup"><span data-stu-id="eea90-120">Associativity</span></span>

 <span data-ttu-id="eea90-121">Когда выражение содержит два или более операторов с одинаковым приоритетом, они вычисляются на основе ассоциативности.</span><span class="sxs-lookup"><span data-stu-id="eea90-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="eea90-122">Операторы с левой ассоциативностью вычисляются слева направо.</span><span class="sxs-lookup"><span data-stu-id="eea90-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="eea90-123">Например, выражение `x * y / z` вычисляется как `(x * y) / z`.</span><span class="sxs-lookup"><span data-stu-id="eea90-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="eea90-124">Операторы с правой ассоциативностью вычисляются справа налево.</span><span class="sxs-lookup"><span data-stu-id="eea90-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="eea90-125">Например, оператор присваивания имеет правую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="eea90-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="eea90-126">Если бы это было не так, следующий код вызвал бы ошибку.</span><span class="sxs-lookup"><span data-stu-id="eea90-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="eea90-127">Другим примером оператора с правой ассоциативностью является троичный оператор ([?:](../../../csharp/language-reference/operators/conditional-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="eea90-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="eea90-128">Большинство двоичных операторов имеют левую ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="eea90-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="eea90-129">Независимо от того, какую ассоциативность (левую или правую) имеют операторы в выражении, сначала вычисляются операнды каждого выражения — слева направо.</span><span class="sxs-lookup"><span data-stu-id="eea90-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="eea90-130">В следующих примерах иллюстрируется порядок вычисления операторов и операндов.</span><span class="sxs-lookup"><span data-stu-id="eea90-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="eea90-131">Оператор</span><span class="sxs-lookup"><span data-stu-id="eea90-131">Statement</span></span>|<span data-ttu-id="eea90-132">Порядок вычислений</span><span class="sxs-lookup"><span data-stu-id="eea90-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="eea90-133">a, b, =</span><span class="sxs-lookup"><span data-stu-id="eea90-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="eea90-134">a, b, c, +, =</span><span class="sxs-lookup"><span data-stu-id="eea90-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="eea90-135">a, b, c, d, \*, +, =</span><span class="sxs-lookup"><span data-stu-id="eea90-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="eea90-136">a, b, c, \*, d, +, =</span><span class="sxs-lookup"><span data-stu-id="eea90-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="eea90-137">a, b, c, -, d, +, =</span><span class="sxs-lookup"><span data-stu-id="eea90-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="eea90-138">a, b, c, -=, +=</span><span class="sxs-lookup"><span data-stu-id="eea90-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="eea90-139">Добавление скобок</span><span class="sxs-lookup"><span data-stu-id="eea90-139">Adding parentheses</span></span>

 <span data-ttu-id="eea90-140">Порядок, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок.</span><span class="sxs-lookup"><span data-stu-id="eea90-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="eea90-141">Например, выражение `2 + 3 * 2` в обычном случае будет иметь значение 8, поскольку операторы умножения выполняются раньше операторов сложения.</span><span class="sxs-lookup"><span data-stu-id="eea90-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="eea90-142">Однако если выражение записано в форме `(2 + 3) * 2`, сложение выполняется перед умножением и в результате получается 10.</span><span class="sxs-lookup"><span data-stu-id="eea90-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="eea90-143">В следующих примерах иллюстрируется порядок вычисления выражений в скобках.</span><span class="sxs-lookup"><span data-stu-id="eea90-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="eea90-144">Как и в предыдущих примерах, перед применением оператора вычисляются операнды.</span><span class="sxs-lookup"><span data-stu-id="eea90-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="eea90-145">Оператор</span><span class="sxs-lookup"><span data-stu-id="eea90-145">Statement</span></span>|<span data-ttu-id="eea90-146">Порядок вычислений</span><span class="sxs-lookup"><span data-stu-id="eea90-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="eea90-147">a, b, c, +, d, \*, =</span><span class="sxs-lookup"><span data-stu-id="eea90-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="eea90-148">a, b, c, d, +, -, =</span><span class="sxs-lookup"><span data-stu-id="eea90-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="eea90-149">a, b, c, +, d, e, -, \*, =</span><span class="sxs-lookup"><span data-stu-id="eea90-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="eea90-150">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="eea90-150">Operator overloading</span></span>

<span data-ttu-id="eea90-151">Можно задать поведение определенных операторов для пользовательских классов и структур.</span><span class="sxs-lookup"><span data-stu-id="eea90-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="eea90-152">Такой процесс называется *перегрузкой операторов*.</span><span class="sxs-lookup"><span data-stu-id="eea90-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="eea90-153">Дополнительные сведения см. в разделе [Перегружаемые операторы](overloadable-operators.md) и статье про ключевое слово [operator](../../language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="eea90-153">For more information, see [Overloadable operators](overloadable-operators.md) and the [operator](../../language-reference/keywords/operator.md) keyword article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eea90-154">См. также</span><span class="sxs-lookup"><span data-stu-id="eea90-154">See also</span></span>

- [<span data-ttu-id="eea90-155">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eea90-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="eea90-156">Инструкции, выражения и операторы</span><span class="sxs-lookup"><span data-stu-id="eea90-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="eea90-157">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="eea90-157">C# Operators</span></span>](../../language-reference/operators/index.md)
