---
title: Справочник по C#. Ключевое слово decimal
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: 7ad01f9e4f5a8b1a153b1ef306e9d6168335eb3d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424306"
---
# <a name="decimal-c-reference"></a><span data-ttu-id="43e08-102">decimal (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="43e08-102">decimal (C# Reference)</span></span>

<span data-ttu-id="43e08-103">Ключевое слово `decimal` обозначает 128-разрядный тип данных.</span><span class="sxs-lookup"><span data-stu-id="43e08-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="43e08-104">По сравнению с другими типами данных с плавающей запятой, диапазон значений `decimal` меньше, а точность выше, благодаря чему этот тип подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="43e08-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="43e08-105">В следующей таблице представлен приблизительный диапазон значений и точность для типа `decimal`.</span><span class="sxs-lookup"><span data-stu-id="43e08-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>

|<span data-ttu-id="43e08-106">Тип</span><span class="sxs-lookup"><span data-stu-id="43e08-106">Type</span></span>|<span data-ttu-id="43e08-107">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="43e08-107">Approximate Range</span></span>|<span data-ttu-id="43e08-108">Точность</span><span class="sxs-lookup"><span data-stu-id="43e08-108">Precision</span></span>|<span data-ttu-id="43e08-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="43e08-109">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|<span data-ttu-id="43e08-110">от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="43e08-110">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="43e08-111">28–29 значащих цифр</span><span class="sxs-lookup"><span data-stu-id="43e08-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="43e08-112">Значением переменной `decimal` по умолчанию является 0m.</span><span class="sxs-lookup"><span data-stu-id="43e08-112">The default value of a `decimal` is 0m.</span></span>

## <a name="literals"></a><span data-ttu-id="43e08-113">Литералы</span><span class="sxs-lookup"><span data-stu-id="43e08-113">Literals</span></span>

<span data-ttu-id="43e08-114">Если требуется, чтобы числовой действительный литерал рассматривался как `decimal`, следует использовать суффикс m или M, например:</span><span class="sxs-lookup"><span data-stu-id="43e08-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>

```csharp
decimal myMoney = 300.5m;
```

<span data-ttu-id="43e08-115">Если суффикс m отсутствует, число рассматривается как [double](../../../csharp/language-reference/keywords/double.md) и возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="43e08-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>

## <a name="conversions"></a><span data-ttu-id="43e08-116">Преобразования</span><span class="sxs-lookup"><span data-stu-id="43e08-116">Conversions</span></span>

<span data-ttu-id="43e08-117">Целочисленные типы неявно преобразуются в тип `decimal` и результатом является тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="43e08-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="43e08-118">Поэтому инициализацию десятичной переменной можно выполнить с помощью целочисленного литерала без суффикса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43e08-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>

```csharp
decimal myMoney = 300;
```

<span data-ttu-id="43e08-119">Неявное преобразование между другими типами с плавающей запятой и типом `decimal` отсутствует, поэтому для преобразования между этими двумя типами следует использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="43e08-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="43e08-120">Например:</span><span class="sxs-lookup"><span data-stu-id="43e08-120">For example:</span></span>

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

<span data-ttu-id="43e08-121">Тип `decimal` можно использовать в одном выражении вместе с целочисленными типами числовых данных.</span><span class="sxs-lookup"><span data-stu-id="43e08-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="43e08-122">Однако использование типа `decimal` вместе с другими типами с плавающей запятой без приведения вызовет ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="43e08-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>

<span data-ttu-id="43e08-123">Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="43e08-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="43e08-124">Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="43e08-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="formatting-decimal-output"></a><span data-ttu-id="43e08-125">Форматирование десятичных выходных данных</span><span class="sxs-lookup"><span data-stu-id="43e08-125">Formatting decimal output</span></span>

<span data-ttu-id="43e08-126">Для форматирования результатов можно воспользоваться методом `String.Format` или методом <xref:System.Console.Write%2A?displayProperty=nameWithType>, вызывающим метод `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="43e08-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="43e08-127">Формат денежных единиц задается с помощью стандартной строки формата денежных единиц "C" или "c", как показано во втором примере далее в данной статье.</span><span class="sxs-lookup"><span data-stu-id="43e08-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="43e08-128">Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43e08-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="43e08-129">Пример</span><span class="sxs-lookup"><span data-stu-id="43e08-129">Example</span></span>

<span data-ttu-id="43e08-130">В приведенном ниже примере возникает ошибка компилятора при попытке сложить переменные типов [double](../../../csharp/language-reference/keywords/double.md) и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="43e08-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

<span data-ttu-id="43e08-131">В результате выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="43e08-131">The result is the following error:</span></span>

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

<span data-ttu-id="43e08-132">В приведенном ниже примере в одном выражении используются переменные типов `decimal` и [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="43e08-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) are mixed in the same expression.</span></span> <span data-ttu-id="43e08-133">В результате возвращается тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="43e08-133">The result evaluates to the `decimal` type.</span></span>

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a><span data-ttu-id="43e08-134">Пример</span><span class="sxs-lookup"><span data-stu-id="43e08-134">Example</span></span>

<span data-ttu-id="43e08-135">В следующем примере для форматирования выходных данных используется строка формата денежных единиц.</span><span class="sxs-lookup"><span data-stu-id="43e08-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="43e08-136">Обратите внимание на округление переменной `x`, поскольку десятичные разряды превышают 0,99 долл. США.</span><span class="sxs-lookup"><span data-stu-id="43e08-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="43e08-137">Переменная `y`, представляющая максимально точные цифры, отображается в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="43e08-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="43e08-138">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="43e08-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="43e08-139">См. также</span><span class="sxs-lookup"><span data-stu-id="43e08-139">See also</span></span>

- <xref:System.Decimal>
- [<span data-ttu-id="43e08-140">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="43e08-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="43e08-141">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="43e08-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="43e08-142">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="43e08-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="43e08-143">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="43e08-143">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="43e08-144">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="43e08-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="43e08-145">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="43e08-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="43e08-146">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="43e08-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="43e08-147">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="43e08-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
