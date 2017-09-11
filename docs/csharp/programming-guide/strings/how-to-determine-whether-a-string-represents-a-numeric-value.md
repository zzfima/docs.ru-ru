---
title: "Практическое руководство. Определение представления числового значения в строке (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
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
ms.openlocfilehash: d2f89f4a4771625389a04f5c92829c91d66eb207
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="ed6c3-102">Практическое руководство. Определение представления числового значения в строке (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="ed6c3-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="ed6c3-103">Чтобы определить, является ли строка допустимым представлением указанного числового типа, воспользуйтесь статическим методом `TryParse`, реализуемым всеми простыми числовыми типами, например <xref:System.DateTime> и <xref:System.Net.IPAddress>.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="ed6c3-104">В следующем примере показано, как определить, является ли число 108 допустимым типом [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="ed6c3-104">The following example shows how to determine whether "108" is a valid [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="ed6c3-105">Если строка содержит нечисловые знаки либо числовое значение слишком велико или мало для указанного типа, `TryParse` возвращает значение "false" и задает выходному параметру значение "0".</span><span class="sxs-lookup"><span data-stu-id="ed6c3-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="ed6c3-106">В противном случае возвращается значение "true", а выходному параметру задается числовое значение строки.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed6c3-107">Строка может содержать только числовые знаки и оставаться недопустимой для типа, где используется метод `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="ed6c3-108">Например, "256" не является допустимым значением для `byte`, однако оно допустимо для `int`.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="ed6c3-109">"98,6" не является допустимым значением для `int`, однако оно допустимо для `decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed6c3-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ed6c3-110">Example</span></span>  
 <span data-ttu-id="ed6c3-111">В следующем примере показано использование `TryParse` со строковыми представлениями значений `long`, `byte` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 <span data-ttu-id="ed6c3-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed6c3-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ed6c3-113">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ed6c3-113">Robust Programming</span></span>  
 <span data-ttu-id="ed6c3-114">Простые числовые типы также реализуют статический метод `Parse`, который вызывает исключение, если строка не является допустимым числом.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-114">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="ed6c3-115">В целом оператор `TryParse` более эффективен, поскольку если число не является допустимым, он просто возвращает значение "false".</span><span class="sxs-lookup"><span data-stu-id="ed6c3-115">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ed6c3-116">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed6c3-116">.NET Framework Security</span></span>  
 <span data-ttu-id="ed6c3-117">Для проверки данных, введенных пользователем в такие элементы управления, как текстовые поля и поля со списком, всегда следует использовать метод `TryParse` или `Parse`.</span><span class="sxs-lookup"><span data-stu-id="ed6c3-117">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6c3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ed6c3-118">See Also</span></span>  
 <span data-ttu-id="ed6c3-119">[Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c3-119">[How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span></span>  
 <span data-ttu-id="ed6c3-120">[Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c3-120">[How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span></span>  
 <span data-ttu-id="ed6c3-121">[Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c3-121">[How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span></span>  
 <span data-ttu-id="ed6c3-122">[Анализ числовых строк](../../../standard/base-types/parsing-numeric.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c3-122">[Parsing Numeric Strings](../../../standard/base-types/parsing-numeric.md) </span></span>  
 [<span data-ttu-id="ed6c3-123">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="ed6c3-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

