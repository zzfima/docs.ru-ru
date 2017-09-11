---
title: "Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
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
ms.openlocfilehash: 312b18e6bf30ace166435e51b1b83937b5c6bf38
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="00936-102">Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="00936-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="00936-103">В следующих примерах кода показано выполнение указанных ниже задач.</span><span class="sxs-lookup"><span data-stu-id="00936-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="00936-104">Получение шестнадцатеричного значения каждого символа в [string](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="00936-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="00936-105">Получение [char](../../../csharp/language-reference/keywords/char.md), соответствующего каждому значению в шестнадцатеричной строке.</span><span class="sxs-lookup"><span data-stu-id="00936-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="00936-106">Преобразование шестнадцатеричного значения `string` в [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="00936-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="00936-107">Преобразование шестнадцатеричного значения `string` в [float](../../../csharp/language-reference/keywords/float.md).</span><span class="sxs-lookup"><span data-stu-id="00936-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="00936-108">Преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричное значение `string`.</span><span class="sxs-lookup"><span data-stu-id="00936-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00936-109">Пример</span><span class="sxs-lookup"><span data-stu-id="00936-109">Example</span></span>  
 <span data-ttu-id="00936-110">Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`.</span><span class="sxs-lookup"><span data-stu-id="00936-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="00936-111">Сначала выполняется разбор `string` до массива символов.</span><span class="sxs-lookup"><span data-stu-id="00936-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="00936-112">Затем, чтобы получить числовое значение каждого символа, для каждого из них вызывается метод <xref:System.Convert.ToInt32%28System.Char%29>.</span><span class="sxs-lookup"><span data-stu-id="00936-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="00936-113">В конце формат числа меняется на шестнадцатеричный в `string`.</span><span class="sxs-lookup"><span data-stu-id="00936-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 <span data-ttu-id="00936-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="00936-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00936-115">Пример</span><span class="sxs-lookup"><span data-stu-id="00936-115">Example</span></span>  
 <span data-ttu-id="00936-116">В этом примере анализируется `string` шестнадцатеричных значений и выводится символ, соответствующий каждому шестнадцатеричному значению.</span><span class="sxs-lookup"><span data-stu-id="00936-116">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="00936-117">Сначала вызывается метод [Split(Char\[\])](xref:System.String.Split(System.Char[])) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве.</span><span class="sxs-lookup"><span data-stu-id="00936-117">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="00936-118">Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>, который преобразует шестнадцатеричное значение в десятичное, представленное в [целое число](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="00936-118">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="00936-119">В примере показано два разных способа получения символа, соответствующего этому коду символа.</span><span class="sxs-lookup"><span data-stu-id="00936-119">It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="00936-120">В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, который возвращает символ, соответствующий целочисленному аргументу, в виде `string`.</span><span class="sxs-lookup"><span data-stu-id="00936-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="00936-121">По второму способу выполняется явное приведение `int` к [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="00936-121">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 <span data-ttu-id="00936-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="00936-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00936-123">Пример</span><span class="sxs-lookup"><span data-stu-id="00936-123">Example</span></span>  
 <span data-ttu-id="00936-124">В этом примере показан еще один способ преобразования шестнадцатеричного `string` в целое число — с помощью метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> .</span><span class="sxs-lookup"><span data-stu-id="00936-124">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 <span data-ttu-id="00936-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="00936-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00936-126">Пример</span><span class="sxs-lookup"><span data-stu-id="00936-126">Example</span></span>  
 <span data-ttu-id="00936-127">В следующем примере показано преобразование шестнадцатеричного `string` в [число с плавающей запятой](../../../csharp/language-reference/keywords/float.md) с помощью класса <xref:System.BitConverter?displayProperty=fullName> и метод <xref:System.Int32.Parse%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="00936-127">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=fullName> class and the <xref:System.Int32.Parse%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="00936-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="00936-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00936-129">Пример</span><span class="sxs-lookup"><span data-stu-id="00936-129">Example</span></span>  
 <span data-ttu-id="00936-130">В следующем примере показано преобразование массива [байтов](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="00936-130">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="00936-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="00936-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00936-132">См. также</span><span class="sxs-lookup"><span data-stu-id="00936-132">See Also</span></span>  
 <span data-ttu-id="00936-133">[Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="00936-133">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="00936-134">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="00936-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 [<span data-ttu-id="00936-135">Практическое руководство. Определение представления числового значения в строке</span><span class="sxs-lookup"><span data-stu-id="00936-135">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

