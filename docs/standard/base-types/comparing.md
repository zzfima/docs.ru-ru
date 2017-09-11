---
title: "Сравнение строк"
description: "Сравнение строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a><span data-ttu-id="f2d10-104">Сравнение строк</span><span class="sxs-lookup"><span data-stu-id="f2d10-104">Comparing strings</span></span>

<span data-ttu-id="f2d10-105">Платформа .NET обеспечивает несколько методов для сравнения значений строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="f2d10-106">В таблице ниже перечислены и описаны методы сравнения значений.</span><span class="sxs-lookup"><span data-stu-id="f2d10-106">The following table lists and describes the value-comparison methods.</span></span>

<span data-ttu-id="f2d10-107">Имя метода</span><span class="sxs-lookup"><span data-stu-id="f2d10-107">Method name</span></span> | <span data-ttu-id="f2d10-108">Применение</span><span class="sxs-lookup"><span data-stu-id="f2d10-108">Use</span></span>
----------- | ---
<span data-ttu-id="f2d10-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="f2d10-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="f2d10-110">Сравнивает значения двух строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-110">Compares the values of two strings.</span></span> <span data-ttu-id="f2d10-111">Возвращает целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-111">Returns an integer value.</span></span>
<span data-ttu-id="f2d10-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="f2d10-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="f2d10-113">Сравнивает две строки без учета локального языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="f2d10-113">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="f2d10-114">Возвращает целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-114">Returns an integer value.</span></span>
<span data-ttu-id="f2d10-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="f2d10-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="f2d10-116">Сравнивает текущий строковый объект с другой строкой.</span><span class="sxs-lookup"><span data-stu-id="f2d10-116">Compares the current string object to another string.</span></span> <span data-ttu-id="f2d10-117">Возвращает целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-117">Returns an integer value.</span></span>
<span data-ttu-id="f2d10-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span><span class="sxs-lookup"><span data-stu-id="f2d10-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span></span> | <span data-ttu-id="f2d10-119">Определяет, начинается ли строка с переданной строки.</span><span class="sxs-lookup"><span data-stu-id="f2d10-119">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="f2d10-120">Возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-120">Returns a Boolean value.</span></span>
<span data-ttu-id="f2d10-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="f2d10-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="f2d10-122">Определяет, заканчивается ли строка переданной строкой.</span><span class="sxs-lookup"><span data-stu-id="f2d10-122">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="f2d10-123">Возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-123">Returns a Boolean value.</span></span>
<span data-ttu-id="f2d10-124">[String.Equals](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="f2d10-124">[String.Equals](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="f2d10-125">Определяет, совпадают ли две строки.</span><span class="sxs-lookup"><span data-stu-id="f2d10-125">Determines whether two strings are the same.</span></span> <span data-ttu-id="f2d10-126">Возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-126">Returns a Boolean value.</span></span>
<span data-ttu-id="f2d10-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="f2d10-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span></span> | <span data-ttu-id="f2d10-128">Возвращает индекс позиции символа или строки начиная с начала проверяемой строки.</span><span class="sxs-lookup"><span data-stu-id="f2d10-128">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="f2d10-129">Возвращает целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-129">Returns an integer value.</span></span>
<span data-ttu-id="f2d10-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="f2d10-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span></span> | <span data-ttu-id="f2d10-131">Возвращает индекс позиции символа или строки начиная с конца проверяемой строки.</span><span class="sxs-lookup"><span data-stu-id="f2d10-131">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="f2d10-132">Возвращает целочисленное значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-132">Returns an integer value.</span></span>

## <a name="compare"></a><span data-ttu-id="f2d10-133">Сравнение</span><span class="sxs-lookup"><span data-stu-id="f2d10-133">Compare</span></span>

<span data-ttu-id="f2d10-134">Статический метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) позволяет тщательно сравнивать две строки.</span><span class="sxs-lookup"><span data-stu-id="f2d10-134">The static [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="f2d10-135">Этот метод учитывает язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="f2d10-135">This method is culturally aware.</span></span> <span data-ttu-id="f2d10-136">Эту функцию можно использовать для сравнения двух строк или подстрок двух строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-136">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="f2d10-137">Кроме того, имеются перегруженные методы, которые учитывают или не учитывают регистр и вариативность языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="f2d10-137">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="f2d10-138">В таблице ниже приведены три целочисленных значения, которые может возвращать этот метод.</span><span class="sxs-lookup"><span data-stu-id="f2d10-138">The following table shows the three integer values that this method might return.</span></span> 

<span data-ttu-id="f2d10-139">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2d10-139">Return value</span></span> | <span data-ttu-id="f2d10-140">Условие</span><span class="sxs-lookup"><span data-stu-id="f2d10-140">Condition</span></span>
------------ | ---------
<span data-ttu-id="f2d10-141">Отрицательное целое число</span><span class="sxs-lookup"><span data-stu-id="f2d10-141">A negative integer</span></span> | <span data-ttu-id="f2d10-142">Первая строка предшествует второй в порядке сортировки или первая строка имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-142">The first string precedes the second string in the sort order, or the first string is `null`.</span></span>
<span data-ttu-id="f2d10-143">0</span><span class="sxs-lookup"><span data-stu-id="f2d10-143">0</span></span> | <span data-ttu-id="f2d10-144">Первая и вторая строка равны или обе строки имеют значения `null`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-144">The first string and the second string are equal, or both strings are `null`.</span></span>
<span data-ttu-id="f2d10-145">Положительное целое число или 1</span><span class="sxs-lookup"><span data-stu-id="f2d10-145">A positive integer, or 1</span></span> | <span data-ttu-id="f2d10-146">Первая строка следует за второй в порядке сортировки или вторая строка имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f2d10-146">The first string follows the second string in the sort order, or the second string is null.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="f2d10-147">Метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) в основном предназначен для использования при упорядочивании или сортировке строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-147">The [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="f2d10-148">Не следует использовать метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой).</span><span class="sxs-lookup"><span data-stu-id="f2d10-148">You should not use the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="f2d10-149">Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="f2d10-149">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="f2d10-150">В примере ниже метод [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) используется для определения относительных значений двух строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-150">The following example uses the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to determine the relative values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

<span data-ttu-id="f2d10-151">Этот пример выводит на консоль значение `-1`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-151">This example displays `-1` to the console.</span></span>

## <a name="compareordinal"></a><span data-ttu-id="f2d10-152">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="f2d10-152">CompareOrdinal</span></span>

<span data-ttu-id="f2d10-153">Метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) сравнивает два строковых объекта без учета локального языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="f2d10-153">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="f2d10-154">Возвращаемые этим методом значения идентичны значениям, возвращаемым методом `Compare` в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="f2d10-154">The return values of this method are identical to the values returned by the `Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2d10-155">Метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) в основном предназначен для использования при упорядочивании или сортировке строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-155">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="f2d10-156">Не следует использовать метод [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой).</span><span class="sxs-lookup"><span data-stu-id="f2d10-156">You should not use the [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="f2d10-157">Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="f2d10-157">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="f2d10-158">В примере ниже метод `CompareOrdinal` используется для сравнения значений двух строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-158">The following example uses the `CompareOrdinal` method to compare the values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

<span data-ttu-id="f2d10-159">Этот пример выводит на консоль значение `-32`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-159">This example displays `-32` to the console.</span></span>

## <a name="compareto"></a><span data-ttu-id="f2d10-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="f2d10-160">CompareTo</span></span>

<span data-ttu-id="f2d10-161">Метод [String.CompareTo](xref:System.String.CompareTo(System.String)) сравнивает строку, которую инкапсулирует текущий строковый объект, с другой строкой или объектом.</span><span class="sxs-lookup"><span data-stu-id="f2d10-161">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="f2d10-162">Возвращаемые этим методом значения идентичны значениям, возвращаемым методом `String.Compare` в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="f2d10-162">The return values of this method are identical to the values returned by the `String.Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2d10-163">Метод [String.CompareTo](xref:System.String.CompareTo(System.String)) в основном предназначен для использования при упорядочивании или сортировке строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-163">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="f2d10-164">Не следует использовать метод [String.CompareTo](xref:System.String.CompareTo(System.String)) для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой).</span><span class="sxs-lookup"><span data-stu-id="f2d10-164">You should not use the [String.CompareTo](xref:System.String.CompareTo(System.String)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="f2d10-165">Для определения равенства двух строк используйте метод [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="f2d10-165">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="f2d10-166">В примере ниже метод `String.CompareTo` используется для сравнения объекта `string1` с объектом `string2`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-166">The following example uses the `String.CompareTo` method to compare the `string1` object to the `string2` object.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

<span data-ttu-id="f2d10-167">Этот пример выводит на консоль значение `-1`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-167">This example displays `-1` to the console.</span></span>

## <a name="equals"></a><span data-ttu-id="f2d10-168">Равно</span><span class="sxs-lookup"><span data-stu-id="f2d10-168">Equals</span></span>

<span data-ttu-id="f2d10-169">С помощью метода [String.Equals](xref:System.String.CompareTo(System.String)) можно легко определить идентичность двух строк.</span><span class="sxs-lookup"><span data-stu-id="f2d10-169">The [String.Equals](xref:System.String.CompareTo(System.String)) method can easily determine if two strings are the same.</span></span> <span data-ttu-id="f2d10-170">Этот метод учитывает регистр и возвращает логическое значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-170">This case-sensitive method returns a `true` or `false` Boolean value.</span></span> <span data-ttu-id="f2d10-171">Метод можно вызывать из существующего класса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f2d10-171">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="f2d10-172">В примере ниже метод `Equals` используется для определения того, содержит ли строковый объект фразу "Hello World".</span><span class="sxs-lookup"><span data-stu-id="f2d10-172">The following example uses the `Equals` method to determine whether a string object contains the phrase "Hello World".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

<span data-ttu-id="f2d10-173">Этот пример выводит на консоль значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-173">This example displays `true` to the console.</span></span>

<span data-ttu-id="f2d10-174">Этот метод также можно использовать как статический.</span><span class="sxs-lookup"><span data-stu-id="f2d10-174">This method can also be used as a static method.</span></span> <span data-ttu-id="f2d10-175">В примере ниже два строковых объекта сравниваются с помощью статического метода.</span><span class="sxs-lookup"><span data-stu-id="f2d10-175">The following example compares two string objects using a static method.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

<span data-ttu-id="f2d10-176">Этот пример выводит на консоль значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-176">This example displays `true` to the console.</span></span>

## <a name="startswith-and-endswith"></a><span data-ttu-id="f2d10-177">StartsWith и EndsWith</span><span class="sxs-lookup"><span data-stu-id="f2d10-177">StartsWith and EndsWith</span></span>

<span data-ttu-id="f2d10-178">Метод [String.StartsWith](xref:System.String.StartsWith(System.String)) можно использовать для определения того, начинается ли строковый объект с тех же символов, которые включает другая строка.</span><span class="sxs-lookup"><span data-stu-id="f2d10-178">You can use the [String.StartsWith](xref:System.String.StartsWith(System.String)) method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="f2d10-179">Этот метод учитывает регистр и возвращает значение `true`, если текущий строковый объект начинается с переданной строки, и значение `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="f2d10-179">This case-sensitive method returns `true` if the current string object begins with the passed string and `false` if it does not.</span></span> <span data-ttu-id="f2d10-180">В примере ниже этот метод используется для определения того, начинается ли строковый объект со слова "Hello".</span><span class="sxs-lookup"><span data-stu-id="f2d10-180">The following example uses this method to determine if a string object begins with "Hello".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

<span data-ttu-id="f2d10-181">Этот пример выводит на консоль значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-181">This example displays `true` to the console.</span></span>

<span data-ttu-id="f2d10-182">Метод [String.EndsWith](xref:System.String.CompareTo(System.String)) сравнивает переданную строку с символами, находящимися в конце текущего строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="f2d10-182">The [String.EndsWith](xref:System.String.CompareTo(System.String)) method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="f2d10-183">Он также возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="f2d10-183">It also returns a Boolean value.</span></span> <span data-ttu-id="f2d10-184">В примере ниже конец строки проверяется с помощью метода `EndsWith`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-184">The following example checks the end of a string using the `EndsWith` method.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

<span data-ttu-id="f2d10-185">Этот пример выводит на консоль значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-185">This example displays `false` to the console.</span></span>

## <a name="indexof-and-lastindexof"></a><span data-ttu-id="f2d10-186">IndexOf и LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="f2d10-186">IndexOf and LastIndexOf</span></span>

<span data-ttu-id="f2d10-187">С помощью метода [String.IndexOf](xref:System.String.IndexOf(System.Char)) можно определить позицию первого вхождения конкретного символа в строку.</span><span class="sxs-lookup"><span data-stu-id="f2d10-187">You can use the [String.IndexOf](xref:System.String.IndexOf(System.Char)) method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="f2d10-188">Этот метод учитывает регистр и начинает отсчет с начала строки. Он возвращает позицию переданного символа, используя отсчитываемый от нуля индекс.</span><span class="sxs-lookup"><span data-stu-id="f2d10-188">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="f2d10-189">Если символ не удается найти, возвращается значение –1.</span><span class="sxs-lookup"><span data-stu-id="f2d10-189">If the character cannot be found, a value of –1 is returned.</span></span>

<span data-ttu-id="f2d10-190">В примере ниже метод `IndexOf` используется для поиска первого вхождения символа "`l`" в строку.</span><span class="sxs-lookup"><span data-stu-id="f2d10-190">The following example uses the `IndexOf` method to search for the first occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

<span data-ttu-id="f2d10-191">Этот пример выводит на консоль значение `2`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-191">This example displays `2` to the console.</span></span>

<span data-ttu-id="f2d10-192">Метод [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) аналогичен методу `String.IndexOf` за исключением того, что он возвращает позицию последнего вхождения конкретного символа в строку.</span><span class="sxs-lookup"><span data-stu-id="f2d10-192">The [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) method is similar to the `String.IndexOf` method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="f2d10-193">Он учитывает регистр и использует отсчитываемый от нуля индекс.</span><span class="sxs-lookup"><span data-stu-id="f2d10-193">It is case-sensitive and uses a zero-based index.</span></span> 

<span data-ttu-id="f2d10-194">В примере ниже метод `LastIndexOf` используется для поиска последнего вхождения символа "`l`" в строку.</span><span class="sxs-lookup"><span data-stu-id="f2d10-194">The following example uses the `LastIndexOf` method to search for the last occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

<span data-ttu-id="f2d10-195">Этот пример выводит на консоль значение `9`.</span><span class="sxs-lookup"><span data-stu-id="f2d10-195">This example displays `9` to the console.</span></span>

<span data-ttu-id="f2d10-196">Оба метода полезно использовать в сочетании с методом [String.Remove](xref:System.String.Remove(System.Int32)).</span><span class="sxs-lookup"><span data-stu-id="f2d10-196">Both methods are useful when used in conjunction with the [String.Remove](xref:System.String.Remove(System.Int32)) method.</span></span> <span data-ttu-id="f2d10-197">Для получения позиции символа используется метод `IndexOf` или `LastIndexOf`, после чего эта позиция передается методу `Remove method` для удаления символа или начинающегося с него слова.</span><span class="sxs-lookup"><span data-stu-id="f2d10-197">You can use either the `IndexOf` or `LastIndexOf` methods to retrieve the position of a character, and then supply that position to the `Remove method` in order to remove a character or a word that begins with that character.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d10-198">См. также</span><span class="sxs-lookup"><span data-stu-id="f2d10-198">See Also</span></span>

[<span data-ttu-id="f2d10-199">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="f2d10-199">Basic string operations</span></span>](basic-string-operations.md)













