---
title: Ключевое слово float (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: 98f89ba3d79f7679b69ce10fd875b3caf69c5257
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157708"
---
# <a name="float-c-reference"></a><span data-ttu-id="90804-102">float (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="90804-102">float (C# Reference)</span></span>

<span data-ttu-id="90804-103">Ключевое слово `float` обозначает простой тип, в котором хранятся 32-разрядные значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="90804-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="90804-104">В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `float`.</span><span class="sxs-lookup"><span data-stu-id="90804-104">The following table shows the precision and approximate range for the `float` type.</span></span>

|<span data-ttu-id="90804-105">Тип</span><span class="sxs-lookup"><span data-stu-id="90804-105">Type</span></span>|<span data-ttu-id="90804-106">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="90804-106">Approximate range</span></span>|<span data-ttu-id="90804-107">Точность</span><span class="sxs-lookup"><span data-stu-id="90804-107">Precision</span></span>|<span data-ttu-id="90804-108">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="90804-108">.NET type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="90804-109">От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="90804-109">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="90804-110">7 знака</span><span class="sxs-lookup"><span data-stu-id="90804-110">7 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a><span data-ttu-id="90804-111">Литералы</span><span class="sxs-lookup"><span data-stu-id="90804-111">Literals</span></span>

<span data-ttu-id="90804-112">По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="90804-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="90804-113">Таким образом, для инициализации переменной с плавающей запятой следует использовать суффикс `f` или `F`, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="90804-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>

```csharp
float x = 3.5F;
```

<span data-ttu-id="90804-114">Если этот суффикс не указан в предыдущем объявлении, вы получите ошибку компиляции, поскольку пытаетесь сохранить значение [double](double.md) в переменную `float`.</span><span class="sxs-lookup"><span data-stu-id="90804-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>

## <a name="conversions"></a><span data-ttu-id="90804-115">Преобразования</span><span class="sxs-lookup"><span data-stu-id="90804-115">Conversions</span></span>

<span data-ttu-id="90804-116">В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="90804-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="90804-117">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="90804-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="90804-118">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="90804-118">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="90804-119">Если одним из типов с плавающей запятой является [double](double.md), то выражение оценивается как [double](double.md) или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="90804-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md), or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

- <span data-ttu-id="90804-120">Если в выражении нет типа [double](double.md), выражение оценивается как `float` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="90804-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="90804-121">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="90804-121">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="90804-122">Положительный и отрицательный ноль</span><span class="sxs-lookup"><span data-stu-id="90804-122">Positive and negative zero</span></span>

- <span data-ttu-id="90804-123">Положительная и отрицательная бесконечность</span><span class="sxs-lookup"><span data-stu-id="90804-123">Positive and negative infinity</span></span>

- <span data-ttu-id="90804-124">Нечисловое значение (NaN)</span><span class="sxs-lookup"><span data-stu-id="90804-124">Not-a-Number value (NaN)</span></span>

- <span data-ttu-id="90804-125">Конечный набор ненулевых значений</span><span class="sxs-lookup"><span data-stu-id="90804-125">The finite set of nonzero values</span></span>

<span data-ttu-id="90804-126">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="90804-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) website.</span></span>

## <a name="example"></a><span data-ttu-id="90804-127">Пример</span><span class="sxs-lookup"><span data-stu-id="90804-127">Example</span></span>

<span data-ttu-id="90804-128">В следующем примере [int](int.md), [short](short.md) и `float` включены в математическое выражение и дают результат `float`.</span><span class="sxs-lookup"><span data-stu-id="90804-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="90804-129">(Помните, что `float` — это псевдоним для типа <xref:System.Single?displayProperty=nameWithType>.) Обратите внимание, что в выражении нет типа [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="90804-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="90804-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="90804-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="90804-131">См. также</span><span class="sxs-lookup"><span data-stu-id="90804-131">See also</span></span>

- <xref:System.Single>  
- [<span data-ttu-id="90804-132">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="90804-132">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="90804-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="90804-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="90804-134">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="90804-134">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="90804-135">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="90804-135">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="90804-136">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="90804-136">Integral Types Table</span></span>](integral-types-table.md)  
- [<span data-ttu-id="90804-137">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="90804-137">Built-In Types Table</span></span>](built-in-types-table.md)  
- [<span data-ttu-id="90804-138">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="90804-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="90804-139">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="90804-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)  