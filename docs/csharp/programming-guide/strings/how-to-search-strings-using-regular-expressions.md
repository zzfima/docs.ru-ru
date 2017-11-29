---
title: "Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="91f88-102">Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="91f88-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="91f88-103">Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> можно использовать для поиска строк.</span><span class="sxs-lookup"><span data-stu-id="91f88-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class can be used to search strings.</span></span> <span data-ttu-id="91f88-104">Это может быть как простейший, так и полноценный поиск с использованием всех возможностей регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="91f88-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="91f88-105">Ниже приведены два примера поиска строк с использованием класса <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="91f88-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="91f88-106">Дополнительные сведения см. в разделе [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="91f88-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91f88-107">Пример</span><span class="sxs-lookup"><span data-stu-id="91f88-107">Example</span></span>  
 <span data-ttu-id="91f88-108">В следующем коде реализуется консольное приложение, выполняющее простой поиск без учета регистра символов по строкам массива.</span><span class="sxs-lookup"><span data-stu-id="91f88-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="91f88-109">Статический метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> выполняет поиск заданного шаблона в указанной строке.</span><span class="sxs-lookup"><span data-stu-id="91f88-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="91f88-110">В этом случае третий аргумент определяет, необходимо ли учитывать регистр символов.</span><span class="sxs-lookup"><span data-stu-id="91f88-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="91f88-111">Для получения дополнительной информации см. <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91f88-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="91f88-112">Пример</span><span class="sxs-lookup"><span data-stu-id="91f88-112">Example</span></span>  
 <span data-ttu-id="91f88-113">В следующем коде реализуется консольное приложение для проверки формата каждой строки в массиве с использованием регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="91f88-113">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="91f88-114">По условиям проверки каждая строка должна иметь формат номера телефона: три группы цифр, разделенных дефисами. Первые две группы содержат по три цифры, и третья группа состоит из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="91f88-114">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="91f88-115">Для этого используется регулярное выражение `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="91f88-115">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="91f88-116">Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="91f88-116">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="91f88-117">См. также</span><span class="sxs-lookup"><span data-stu-id="91f88-117">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [<span data-ttu-id="91f88-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="91f88-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="91f88-119">Строки</span><span class="sxs-lookup"><span data-stu-id="91f88-119">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="91f88-120">Регулярные выражения в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="91f88-120">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)  
 [<span data-ttu-id="91f88-121">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="91f88-121">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
