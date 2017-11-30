---
title: "Пример регулярного выражения. Поиск ссылок HREF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="9ce5a-102">Пример регулярного выражения. Поиск ссылок HREF</span><span class="sxs-lookup"><span data-stu-id="9ce5a-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="9ce5a-103">В следующем примере показаны поиск и вывод всех значений href="...", а также их позиций в строке.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="9ce5a-104">Объект Regex</span><span class="sxs-lookup"><span data-stu-id="9ce5a-104">The Regex Object</span></span>  
 <span data-ttu-id="9ce5a-105">Поскольку `DumpHRefs` метод может вызываться несколько раз из пользовательского кода, он использует `static` (`Shared` в Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9ce5a-106">Это позволяет обработчику регулярных выражений кэшировать регулярное выражение и избежать дополнительной нагрузки, создания нового <xref:System.Text.RegularExpressions.Regex> объекта при каждом вызове метода.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="9ce5a-107">Объект <xref:System.Text.RegularExpressions.Match> объект затем используется для перебора всех совпадений в строке.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="9ce5a-108">В следующем примере показан вызов метода `DumpHRefs`.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="9ce5a-109">Возможные интерпретации шаблона регулярного выражения `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="9ce5a-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="9ce5a-110">Pattern</span></span>|<span data-ttu-id="9ce5a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9ce5a-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="9ce5a-112">Совпадение с литеральной строкой "href".</span><span class="sxs-lookup"><span data-stu-id="9ce5a-112">Match the literal string "href".</span></span> <span data-ttu-id="9ce5a-113">Сопоставление не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="9ce5a-114">Соответствует нулю или нескольким символам пробела.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="9ce5a-115">Совпадает со знака равенства.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="9ce5a-116">Соответствует нулю или нескольким символам пробела.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="9ce5a-117">Полностью соответствовать одному из следующих без назначения результата захватываемой группе:</span><span class="sxs-lookup"><span data-stu-id="9ce5a-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="9ce5a-118">-Кавычки или апострофа, за которым следует ноль или более вхождений любых символов, кроме кавычки или апострофа, следуют кавычки или апостроф.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="9ce5a-119">В этот шаблон включена группа с именем `1`.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="9ce5a-120">— Один или несколько знаков пустого пространства.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="9ce5a-121">В этот шаблон включена группа с именем `1`.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="9ce5a-122">Присвоить ноль или несколько любых символов, кроме кавычки или апострофа, группе записи `1`.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="9ce5a-123">Присвоить один или несколько символов, отличных от пробела, захваченной группе с именем `1`.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="9ce5a-124">Класс результата поиска</span><span class="sxs-lookup"><span data-stu-id="9ce5a-124">Match Result Class</span></span>  
 <span data-ttu-id="9ce5a-125">Результаты поиска, хранятся в <xref:System.Text.RegularExpressions.Match> класса, который предоставляет доступ к все подстроки, извлеченным при поиске.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="9ce5a-126">Также запоминается искомая строка и используемое регулярное выражение, чтобы оно могло вызвать <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> метод для выполнения другого поиска, начиная с того места, где закончилось последнее из них.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="9ce5a-127">Явно именованные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9ce5a-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="9ce5a-128">В обычных регулярных выражениях круглые скобки, обозначающие отдельные шаблоны, автоматически последовательно нумеруются.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="9ce5a-129">В связи с этим возникают две проблемы.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-129">This leads to two problems.</span></span> <span data-ttu-id="9ce5a-130">Во-первых, если регулярное выражение изменяется из-за вставки или удаления пары круглых скобок, все части кода, которые ссылаются на нумерованные шаблоны, необходимо переписать, чтобы отразить новую нумерацию.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="9ce5a-131">Во-вторых, вследствие того, что различные пары круглых скобок часто используются для определения двух альтернативных выражений для поиска, трудно определить, какое из двух выражений в действительности вернуло результат.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="9ce5a-132">Для решения этих проблем <xref:System.Text.RegularExpressions.Regex> класс поддерживает синтаксис `(?<name>…)` для отслеживания соответствия в указанной области (области, можно назвать с помощью string или integer; целые числа работают быстрее).</span><span class="sxs-lookup"><span data-stu-id="9ce5a-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="9ce5a-133">Таким образом, если совпадение будет найдено повторно, оно попадет в ту же ячейку.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="9ce5a-134">В случае конфликта успешным является то совпадение, которое было помещено в ячейку последним.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="9ce5a-135">(Однако доступен и полный список совпадений для одной ячейки.</span><span class="sxs-lookup"><span data-stu-id="9ce5a-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="9ce5a-136">В разделе <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> Дополнительные сведения.)</span><span class="sxs-lookup"><span data-stu-id="9ce5a-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce5a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9ce5a-137">See Also</span></span>  
 [<span data-ttu-id="9ce5a-138">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="9ce5a-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
