---
title: "Практическое руководство. Исключение недопустимых символов из строки"
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
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f676ca9121498da7c88cdec8b49586bde91b181
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="0888a-102">Практическое руководство. Исключение недопустимых символов из строки</span><span class="sxs-lookup"><span data-stu-id="0888a-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="0888a-103">В следующем примере используется статический <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> метод для удаления недопустимых символов из строки.</span><span class="sxs-lookup"><span data-stu-id="0888a-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0888a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0888a-104">Example</span></span>  
 <span data-ttu-id="0888a-105">Определенный в этом примере метод `CleanInput` используется для удаления потенциально опасных символов, введенных в текстовое поле пользователем.</span><span class="sxs-lookup"><span data-stu-id="0888a-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="0888a-106">В данном случае `CleanInput` возвращает строку после удаления всех знаков, не являющихся буквенно-цифровыми, за исключением символов "@", "-" (дефис) и "." (точка).</span><span class="sxs-lookup"><span data-stu-id="0888a-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="0888a-107">Однако шаблон регулярного выражения можно изменить таким образом, чтобы исключались все символы, которые не должны входить во входную строку.</span><span class="sxs-lookup"><span data-stu-id="0888a-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="0888a-108">Шаблон регулярного выражения `[^\w\.@-]` ищет совпадения для всех символов, которые не являются словообразующими символами, точкой, символом "@" и дефисом.</span><span class="sxs-lookup"><span data-stu-id="0888a-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="0888a-109">Словообразующий символ — это любая буква, десятичная цифра или любой соединительный знак пунктуации (например, символ подчеркивания).</span><span class="sxs-lookup"><span data-stu-id="0888a-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="0888a-110">Любой символ, который соответствует этому шаблону заменяется <xref:System.String.Empty?displayProperty=nameWithType>, который является строкой, заданной в шаблоне замены.</span><span class="sxs-lookup"><span data-stu-id="0888a-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="0888a-111">Чтобы разрешить дополнительные символы во входной строке, добавьте эти символы в класс символов в шаблоне регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="0888a-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="0888a-112">Например, шаблон регулярного выражения `[^\w\.@-\\%]` также разрешает знак процента и обратную косую черту во входной строке.</span><span class="sxs-lookup"><span data-stu-id="0888a-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0888a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0888a-113">See Also</span></span>  
 [<span data-ttu-id="0888a-114">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="0888a-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
