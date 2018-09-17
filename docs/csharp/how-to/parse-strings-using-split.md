---
title: Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на C#)
description: Метод String.Split возвращает массив строк, разбитых по набору разделителей. Это простой и удобный способ анализа строк.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: b6170be2dbb3f11906bbaa6e5c3be3e48a976246
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45646948"
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="e5ee2-104">Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e5ee2-104">How to: Parse Strings Using String.Split (C# Guide)</span></span>

<span data-ttu-id="e5ee2-105">Метод <xref:System.String.Split%2A?displayProperty=nameWithType> создает массив подстрок, разбивая входную строку по одному или нескольким разделителям.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="e5ee2-106">Часто это самый простой способ разделить строку по границам слов.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="e5ee2-107">Он также используется для разбиения строк по другим конкретным символам или строкам.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="e5ee2-108">Следующий код разбивает обычную фразу на массив строк для каждого слова.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="e5ee2-109">Каждый экземпляр знака разделения создает значение в возвращаемом массиве.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="e5ee2-110">Последовательные знаки разделения создают пустую строку в виде значения в возвращаемом массиве.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="e5ee2-111">Это можно увидеть в следующем примере, где в качестве разделителя используется пробел:</span><span class="sxs-lookup"><span data-stu-id="e5ee2-111">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="e5ee2-112">Такое поведение упрощает работу с такими форматами, как файл данных с разделителями-запятыми (CSV), которые представляют табличные данные.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-112">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="e5ee2-113">Идущие подряд запятые представляют пустой столбец.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="e5ee2-114">Чтобы исключить из возвращаемого массива все пустые строки, можно передать необязательный параметр <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="e5ee2-115">Для более сложной обработки возвращенной коллекции можно использовать [LINQ](../programming-guide/concepts/linq/index.md), чтобы управлять результирующей последовательностью.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="e5ee2-116"><xref:System.String.Split%2A?displayProperty=nameWithType> может использовать несколько знаков разделения.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="e5ee2-117">В приведенном ниже примере в качестве знаков разделения используются пробелы, запятые, точки, двоеточия и символы табуляции, которые передаются в метод <xref:System.String.Split%2A> в виде массива.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="e5ee2-118">Цикл в конце кода отображает каждое из слов в возвращенном массиве.</span><span class="sxs-lookup"><span data-stu-id="e5ee2-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="e5ee2-119">Последовательные экземпляры любого разделителя создают пустую строку в выходном массиве:</span><span class="sxs-lookup"><span data-stu-id="e5ee2-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="e5ee2-120">Метод <xref:System.String.Split%2A?displayProperty=nameWithType> может принимать массив строк (в этом случае в качестве разделителей при анализе целевой строки используются последовательности символов, а не отдельные символы).</span><span class="sxs-lookup"><span data-stu-id="e5ee2-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="e5ee2-121">Вы можете оценить эти примеры, просмотрев код в нашем [репозитории GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="e5ee2-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="e5ee2-122">Или можете загрузить образцы [в ZIP-файле](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="e5ee2-122">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ee2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ee2-123">See Also</span></span>

- [<span data-ttu-id="e5ee2-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e5ee2-124">C# Programming Guide</span></span>](../programming-guide/index.md)  
- [<span data-ttu-id="e5ee2-125">Строки</span><span class="sxs-lookup"><span data-stu-id="e5ee2-125">Strings</span></span>](../programming-guide/strings/index.md)  
- [<span data-ttu-id="e5ee2-126">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="e5ee2-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)
