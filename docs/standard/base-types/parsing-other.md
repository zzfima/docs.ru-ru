---
title: "Разбор других строк в .NET"
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
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="126c4-102">Разбор других строк в .NET</span><span class="sxs-lookup"><span data-stu-id="126c4-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="126c4-103">В дополнение к числовым и <xref:System.DateTime> строки, можно также проанализировать строк, представляющих типы <xref:System.Char>, <xref:System.Boolean>, и <xref:System.Enum> в типы данных.</span><span class="sxs-lookup"><span data-stu-id="126c4-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="126c4-104">Char</span><span class="sxs-lookup"><span data-stu-id="126c4-104">Char</span></span>  
 <span data-ttu-id="126c4-105">Метод статического анализа, связанный с типом данных**Char**, полезен для преобразования строки, содержащей один символ, в его значение в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="126c4-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="126c4-106">В следующем примере кода выполняется разбор строки в символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="126c4-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="126c4-107">Boolean</span><span class="sxs-lookup"><span data-stu-id="126c4-107">Boolean</span></span>  
 <span data-ttu-id="126c4-108">**Логическое** содержит тип данных **проанализировать** метод, который можно использовать для преобразования строки, которая представляет логическое значение, в фактический **логическое** типа.</span><span class="sxs-lookup"><span data-stu-id="126c4-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="126c4-109">Этот метод не учитывает регистр и может успешно анализировать строку, содержащую значения "True" или "False".</span><span class="sxs-lookup"><span data-stu-id="126c4-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="126c4-110">**Проанализировать** метод, связанный с **логическое** тип также можно провести синтаксический анализ строки, окруженные пробельные символы.</span><span class="sxs-lookup"><span data-stu-id="126c4-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="126c4-111">Если передается любая другая строка, <xref:System.FormatException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="126c4-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="126c4-112">Следующий пример кода использует **проанализировать** метод для преобразования строки в логическое значение.</span><span class="sxs-lookup"><span data-stu-id="126c4-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="126c4-113">Перечисление</span><span class="sxs-lookup"><span data-stu-id="126c4-113">Enumeration</span></span>  
 <span data-ttu-id="126c4-114">Статический метод **Parse** можно использовать, чтобы инициализировать значение строки типом перечисления.</span><span class="sxs-lookup"><span data-stu-id="126c4-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="126c4-115">Этот метод принимает разборе тип перечисления, строка для анализа и необязательный логический флаг, указывающее, является ли синтаксический анализ с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="126c4-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="126c4-116">Анализируемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов.</span><span class="sxs-lookup"><span data-stu-id="126c4-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="126c4-117">Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием побитовой операции OR.</span><span class="sxs-lookup"><span data-stu-id="126c4-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="126c4-118">В следующем примере используется **проанализировать** метод для преобразования строкового представления в значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="126c4-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="126c4-119"><xref:System.DayOfWeek> Инициализируется значением перечисления **четверг** из строки.</span><span class="sxs-lookup"><span data-stu-id="126c4-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="126c4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="126c4-120">See Also</span></span>  
 [<span data-ttu-id="126c4-121">Анализ строк в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="126c4-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="126c4-122">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="126c4-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="126c4-123">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="126c4-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
