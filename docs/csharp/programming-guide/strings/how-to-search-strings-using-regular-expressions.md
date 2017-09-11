---
title: "Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="7bcd9-102">Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="7bcd9-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="7bcd9-103">Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> можно использовать для поиска строк.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class can be used to search strings.</span></span> <span data-ttu-id="7bcd9-104">Это может быть как простейший, так и полноценный поиск с использованием всех возможностей регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="7bcd9-105">Ниже приведены два примера поиска строк с использованием класса <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="7bcd9-106">Дополнительные сведения см. в разделе [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bcd9-107">Пример</span><span class="sxs-lookup"><span data-stu-id="7bcd9-107">Example</span></span>  
 <span data-ttu-id="7bcd9-108">В следующем коде реализуется консольное приложение, выполняющее простой поиск без учета регистра символов по строкам массива.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="7bcd9-109">Статический метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> выполняет поиск заданного шаблона в указанной строке.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="7bcd9-110">В этом случае третий аргумент определяет, необходимо ли учитывать регистр символов.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="7bcd9-111">Для получения дополнительной информации см. <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="7bcd9-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bcd9-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bcd9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7bcd9-113">Example</span></span>  
 <span data-ttu-id="7bcd9-114">В следующем коде реализуется консольное приложение для проверки формата каждой строки в массиве с использованием регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-114">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="7bcd9-115">По условиям проверки каждая строка должна иметь формат номера телефона: три группы цифр, разделенных дефисами. Первые две группы содержат по три цифры, и третья группа состоит из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-115">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="7bcd9-116">Для этого используется регулярное выражение `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="7bcd9-116">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="7bcd9-117">Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="7bcd9-117">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 <span data-ttu-id="7bcd9-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bcd9-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcd9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7bcd9-119">See Also</span></span>  
 <span data-ttu-id="7bcd9-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7bcd9-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span></span>   
 <span data-ttu-id="7bcd9-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7bcd9-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7bcd9-122">[Строки](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="7bcd9-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="7bcd9-123">[Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312) </span><span class="sxs-lookup"><span data-stu-id="7bcd9-123">[.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312) </span></span>  
 [<span data-ttu-id="7bcd9-124">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="7bcd9-124">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

