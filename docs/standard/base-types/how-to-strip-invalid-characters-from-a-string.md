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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 030fc003c54e122362d7ecc71675a8b197b68e48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a>Практическое руководство. Исключение недопустимых символов из строки
В следующем примере используется статический метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> для исключения недопустимых символов из строки.  
  
## <a name="example"></a>Пример  
 Определенный в этом примере метод `CleanInput` используется для удаления потенциально опасных символов, введенных в текстовое поле пользователем. В данном случае `CleanInput` возвращает строку после удаления всех знаков, не являющихся буквенно-цифровыми, за исключением символов "@", "-" (дефис) и "." (точка). Однако шаблон регулярного выражения можно изменить таким образом, чтобы исключались все символы, которые не должны входить во входную строку.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 Шаблон регулярного выражения `[^\w\.@-]` ищет совпадения для всех символов, которые не являются словообразующими символами, точкой, символом "@" и дефисом. Словообразующий символ — это любая буква, десятичная цифра или любой соединительный знак пунктуации (например, символ подчеркивания). Все символы, которые совпадают с данным шаблоном, заменяются строкой <xref:System.String.Empty?displayProperty=nameWithType>, которая определяется в шаблоне замены. Чтобы разрешить дополнительные символы во входной строке, добавьте эти символы в класс символов в шаблоне регулярного выражения. Например, шаблон регулярного выражения `[^\w\.@-\\%]` также разрешает использовать знак процента и обратную косую черту во входной строке.  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
