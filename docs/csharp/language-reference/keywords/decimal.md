---
title: "decimal (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c06d14f01302a21427845d0269fc8181a380914
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="decimal-c-reference"></a><span data-ttu-id="8e74c-102">decimal (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8e74c-102">decimal (C# Reference)</span></span>
<span data-ttu-id="8e74c-103">Ключевое слово `decimal` обозначает 128-разрядный тип данных.</span><span class="sxs-lookup"><span data-stu-id="8e74c-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="8e74c-104">По сравнению с другими типами данных с плавающей запятой, диапазон значений `decimal` меньше, а точность выше, благодаря чему этот тип подходит для финансовых расчетов.</span><span class="sxs-lookup"><span data-stu-id="8e74c-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="8e74c-105">В следующей таблице представлен приблизительный диапазон значений и точность для типа `decimal`.</span><span class="sxs-lookup"><span data-stu-id="8e74c-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="8e74c-106">Тип</span><span class="sxs-lookup"><span data-stu-id="8e74c-106">Type</span></span>|<span data-ttu-id="8e74c-107">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="8e74c-107">Approximate Range</span></span>|<span data-ttu-id="8e74c-108">Точность</span><span class="sxs-lookup"><span data-stu-id="8e74c-108">Precision</span></span>|<span data-ttu-id="8e74c-109">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8e74c-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="8e74c-110">(От -7,9 x 10<sup>28</sup> до 7,9 x 10<sup>28</sup>) / (от 10<sup>0</sup> до 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="8e74c-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="8e74c-111">28–29 значащих цифр</span><span class="sxs-lookup"><span data-stu-id="8e74c-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="8e74c-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="8e74c-112">Literals</span></span>  
 <span data-ttu-id="8e74c-113">Если требуется, чтобы числовой действительный литерал рассматривался как `decimal`, следует использовать суффикс m или M, например:</span><span class="sxs-lookup"><span data-stu-id="8e74c-113">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="8e74c-114">Если суффикс m отсутствует, число рассматривается как [double](../../../csharp/language-reference/keywords/double.md) и возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="8e74c-114">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="8e74c-115">Преобразования</span><span class="sxs-lookup"><span data-stu-id="8e74c-115">Conversions</span></span>  
 <span data-ttu-id="8e74c-116">Целочисленные типы неявно преобразуются в тип `decimal` и результатом является тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="8e74c-116">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="8e74c-117">Поэтому инициализацию десятичной переменной можно выполнить с помощью целочисленного литерала без суффикса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8e74c-117">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="8e74c-118">Неявное преобразование между другими типами с плавающей запятой и типом `decimal` отсутствует, поэтому для преобразования между этими двумя типами следует использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="8e74c-118">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="8e74c-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e74c-119">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="8e74c-120">Тип `decimal` можно использовать в одном выражении вместе с целочисленными типами числовых данных.</span><span class="sxs-lookup"><span data-stu-id="8e74c-120">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="8e74c-121">Однако использование типа `decimal` вместе с другими типами с плавающей запятой без приведения вызовет ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="8e74c-121">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="8e74c-122">Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="8e74c-122">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="8e74c-123">Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="8e74c-123">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="8e74c-124">Форматирование десятичных выходных данных</span><span class="sxs-lookup"><span data-stu-id="8e74c-124">Formatting Decimal Output</span></span>  
 <span data-ttu-id="8e74c-125">Для форматирования результатов можно воспользоваться методом `String.Format` или методом <xref:System.Console.Write%2A?displayProperty=fullName>, вызывающим метод `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="8e74c-125">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> method, which calls `String.Format()`.</span></span> <span data-ttu-id="8e74c-126">Формат денежных единиц задается с помощью стандартной строки формата денежных единиц "C" или "c", как показано во втором примере далее в данной статье.</span><span class="sxs-lookup"><span data-stu-id="8e74c-126">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="8e74c-127">Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8e74c-127">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e74c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="8e74c-128">Example</span></span>  
 <span data-ttu-id="8e74c-129">В приведенном ниже примере возникает ошибка компилятора при попытке сложить переменные типов [double](../../../csharp/language-reference/keywords/double.md) и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="8e74c-129">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="8e74c-130">В результате выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="8e74c-130">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="8e74c-131">В приведенном ниже примере в одном выражении используются переменные типов `decimal` и [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="8e74c-131">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="8e74c-132">В результате возвращается тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="8e74c-132">The result evaluates to the `decimal` type.</span></span>  
  
 <span data-ttu-id="8e74c-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e74c-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e74c-134">Пример</span><span class="sxs-lookup"><span data-stu-id="8e74c-134">Example</span></span>  
 <span data-ttu-id="8e74c-135">В следующем примере для форматирования выходных данных используется строка формата денежных единиц.</span><span class="sxs-lookup"><span data-stu-id="8e74c-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="8e74c-136">Обратите внимание на округление переменной `x`, поскольку десятичные разряды превышают 0,99 долл. США.</span><span class="sxs-lookup"><span data-stu-id="8e74c-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="8e74c-137">Переменная `y`, представляющая максимально точные цифры, отображается в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="8e74c-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 <span data-ttu-id="8e74c-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8e74c-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8e74c-139">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8e74c-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e74c-140">См. также</span><span class="sxs-lookup"><span data-stu-id="8e74c-140">See Also</span></span>  
 <span data-ttu-id="8e74c-141"><xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="8e74c-141"><xref:System.Decimal></span></span>   
 <span data-ttu-id="8e74c-142">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8e74c-143">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8e74c-144">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-144">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="8e74c-145">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-145">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="8e74c-146">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-146">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="8e74c-147">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-147">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="8e74c-148">[Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="8e74c-148">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="8e74c-149">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="8e74c-149">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)

