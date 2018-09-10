---
title: Ключевое слово double (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 4c11065d9354d44c1da8354c6f7b4f52d7b84c10
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275396"
---
# <a name="double-c-reference"></a><span data-ttu-id="88f67-102">double (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="88f67-102">double (C# Reference)</span></span>

<span data-ttu-id="88f67-103">Ключевое слово `double` обозначает простой тип, используемый для хранения 64-разрядных значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="88f67-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="88f67-104">В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `double`.</span><span class="sxs-lookup"><span data-stu-id="88f67-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="88f67-105">Тип</span><span class="sxs-lookup"><span data-stu-id="88f67-105">Type</span></span>|<span data-ttu-id="88f67-106">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="88f67-106">Approximate range</span></span>|<span data-ttu-id="88f67-107">Точность</span><span class="sxs-lookup"><span data-stu-id="88f67-107">Precision</span></span>|<span data-ttu-id="88f67-108">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="88f67-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="88f67-109">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="88f67-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="88f67-110">15–16 знаков</span><span class="sxs-lookup"><span data-stu-id="88f67-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="88f67-111">Литералы</span><span class="sxs-lookup"><span data-stu-id="88f67-111">Literals</span></span>

<span data-ttu-id="88f67-112">По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как `double`.</span><span class="sxs-lookup"><span data-stu-id="88f67-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="88f67-113">Если необходимо, чтобы целое число обрабатывалось как `double`, следует использовать суффикс d или D, например:</span><span class="sxs-lookup"><span data-stu-id="88f67-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="88f67-114">Преобразования</span><span class="sxs-lookup"><span data-stu-id="88f67-114">Conversions</span></span>

<span data-ttu-id="88f67-115">В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="88f67-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="88f67-116">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="88f67-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="88f67-117">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="88f67-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="88f67-118">Если одним из типов с плавающей запятой является `double`, то выражение оценивается как `double` или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных сравнениях и сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="88f67-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

- <span data-ttu-id="88f67-119">Если в выражении нет типа `double`, то выражение оценивается как [float](../../../csharp/language-reference/keywords/float.md) или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных сравнениях и сравнениях на равенство.</span><span class="sxs-lookup"><span data-stu-id="88f67-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

 <span data-ttu-id="88f67-120">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="88f67-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="88f67-121">положительный и отрицательный нуль;</span><span class="sxs-lookup"><span data-stu-id="88f67-121">Positive and negative zero.</span></span>

- <span data-ttu-id="88f67-122">положительная и отрицательная бесконечность;</span><span class="sxs-lookup"><span data-stu-id="88f67-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="88f67-123">нечисловое значение (NaN);</span><span class="sxs-lookup"><span data-stu-id="88f67-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="88f67-124">конечный набор ненулевых значений.</span><span class="sxs-lookup"><span data-stu-id="88f67-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="88f67-125">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="88f67-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="88f67-126">Пример</span><span class="sxs-lookup"><span data-stu-id="88f67-126">Example</span></span>

<span data-ttu-id="88f67-127">В следующем примере складываются значения, имеющие типы [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) и `double`. Получается результат, имеющий тип `double`.</span><span class="sxs-lookup"><span data-stu-id="88f67-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="88f67-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="88f67-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="88f67-129">См. также</span><span class="sxs-lookup"><span data-stu-id="88f67-129">See Also</span></span>

- [<span data-ttu-id="88f67-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="88f67-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="88f67-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="88f67-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="88f67-132">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="88f67-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="88f67-133">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="88f67-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="88f67-134">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="88f67-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="88f67-135">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="88f67-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
- [<span data-ttu-id="88f67-136">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="88f67-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="88f67-137">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="88f67-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
