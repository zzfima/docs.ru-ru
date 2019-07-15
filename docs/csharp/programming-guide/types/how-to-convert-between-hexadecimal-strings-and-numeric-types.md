---
title: Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы - руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 2b896fb645113bc33b6a320948770947adc16dab
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661147"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="222c9-102">Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="222c9-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="222c9-103">В следующих примерах кода показано выполнение указанных ниже задач.</span><span class="sxs-lookup"><span data-stu-id="222c9-103">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="222c9-104">Получение шестнадцатеричного значения каждого символа в [string](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="222c9-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
- <span data-ttu-id="222c9-105">Получение [char](../../../csharp/language-reference/keywords/char.md), соответствующего каждому значению в шестнадцатеричной строке.</span><span class="sxs-lookup"><span data-stu-id="222c9-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="222c9-106">Преобразование шестнадцатеричного значения `string` в [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="222c9-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="222c9-107">Преобразование шестнадцатеричного значения `string` в [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="222c9-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="222c9-108">Преобразование массива [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) в шестнадцатеричное значение `string`.</span><span class="sxs-lookup"><span data-stu-id="222c9-108">Convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="222c9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="222c9-109">Example</span></span>  
 <span data-ttu-id="222c9-110">Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`.</span><span class="sxs-lookup"><span data-stu-id="222c9-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="222c9-111">Сначала выполняется разбор `string` до массива символов.</span><span class="sxs-lookup"><span data-stu-id="222c9-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="222c9-112">Затем, чтобы получить числовое значение каждого символа, для каждого из них вызывается метод <xref:System.Convert.ToInt32%28System.Char%29>.</span><span class="sxs-lookup"><span data-stu-id="222c9-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="222c9-113">В конце формат числа меняется на шестнадцатеричный в `string`.</span><span class="sxs-lookup"><span data-stu-id="222c9-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="222c9-114">Пример</span><span class="sxs-lookup"><span data-stu-id="222c9-114">Example</span></span>  
 <span data-ttu-id="222c9-115">В этом примере анализируется `string` шестнадцатеричных значений и выводится символ, соответствующий каждому шестнадцатеричному значению.</span><span class="sxs-lookup"><span data-stu-id="222c9-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="222c9-116">Сначала вызывается метод [Split(Char\[\])](xref:System.String.Split(System.Char[])) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве.</span><span class="sxs-lookup"><span data-stu-id="222c9-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="222c9-117">Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>, который преобразует шестнадцатеричное значение в десятичное, представленное в [целое число](../../../csharp/language-reference/builtin-types/integral-numeric-types.md). В примере показано два разных способа получения символа, соответствующего этому коду символа.</span><span class="sxs-lookup"><span data-stu-id="222c9-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="222c9-118">В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, который возвращает символ, соответствующий целочисленному аргументу, в виде `string`.</span><span class="sxs-lookup"><span data-stu-id="222c9-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="222c9-119">По второму способу выполняется явное приведение `int` к [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="222c9-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="222c9-120">Пример</span><span class="sxs-lookup"><span data-stu-id="222c9-120">Example</span></span>  
 <span data-ttu-id="222c9-121">В этом примере показан еще один способ преобразования шестнадцатеричного `string` в целое число — с помощью метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> .</span><span class="sxs-lookup"><span data-stu-id="222c9-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="222c9-122">Пример</span><span class="sxs-lookup"><span data-stu-id="222c9-122">Example</span></span>  
 <span data-ttu-id="222c9-123">В следующем примере показано преобразование шестнадцатеричного `string` в [число с плавающей запятой](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md) с помощью класса <xref:System.BitConverter?displayProperty=nameWithType> и метод <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="222c9-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="222c9-124">Пример</span><span class="sxs-lookup"><span data-stu-id="222c9-124">Example</span></span>  
 <span data-ttu-id="222c9-125">В следующем примере показано преобразование массива [байтов](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="222c9-125">The following example shows how to convert a [byte](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="222c9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="222c9-126">See also</span></span>

- [<span data-ttu-id="222c9-127">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="222c9-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="222c9-128">Типы</span><span class="sxs-lookup"><span data-stu-id="222c9-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="222c9-129">Практическое руководство. Определение представления числового значения в строке</span><span class="sxs-lookup"><span data-stu-id="222c9-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
