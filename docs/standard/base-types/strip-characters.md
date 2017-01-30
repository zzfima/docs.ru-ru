---
title: "Практическое руководство. Исключение недопустимых символов из строки"
description: "Практическое руководство. Исключение недопустимых символов из строки"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f1df4967-7887-41d2-b60f-0da9be67c8fa
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 2d5b0756ab8c34cca0c4ca7c1eb73f81a7a10b70

---

# <a name="how-to-strip-invalid-characters-from-a-string"></a>Практическое руководство. Исключение недопустимых символов из строки

В следующем примере используется статический метод [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) для исключения недопустимых символов из строки. 

## <a name="example"></a>Пример

Определенный в этом примере метод `CleanInput` используется для удаления потенциально опасных символов, введенных в текстовое поле пользователем. В этом случае `CleanInput` возвращает строку после удаления всех символов, не являющихся буквенно-цифровыми, за исключением символов (@),, "-" (дефис) и "." (точка). Однако шаблон регулярного выражения можно изменить таким образом, чтобы исключались все символы, которые не должны входить во входную строку.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
    static string CleanInput(string strIn)
    {
        // Replace invalid characters with empty strings.
        try {
           return Regex.Replace(strIn, @"[^\w\.@-]", "", 
                                RegexOptions.None, TimeSpan.FromSeconds(1.5)); 
        }
        // If we timeout when replacing invalid characters, 
        // we should return Empty.
        catch (RegexMatchTimeoutException) {
           return String.Empty;   
        }
    }
}
```

```vb
Imports System.Text.RegularExpressions

Module Example
    Function CleanInput(strIn As String) As String
        ' Replace invalid characters with empty strings.
        Try
           Return Regex.Replace(strIn, "[^\w\.@-]", "")
        ' If we timeout when replacing invalid characters, 
        ' we should return String.Empty.
        Catch e As RegexMatchTimeoutException
           Return String.Empty         
        End Try
    End Function
End Module
```

Шаблон регулярного выражения `[^\w\.@-]` ищет совпадения для всех символов, которые не являются словообразующими символами, точкой, символом @ или дефисом. Словообразующий символ — это любая буква, десятичная цифра или любой соединительный знак пунктуации (например, символ подчеркивания). Все символы, которые совпадают с данным шаблоном, заменяются строкой [String.Empty](xref:System.String.Empty), которая является строкой, заданной в шаблоне замены. Чтобы разрешить дополнительные символы во входной строке, добавьте эти символы в класс символов в шаблоне регулярного выражения. Например, шаблон регулярного выражения `[^\w\.@-\\%]` также разрешает знак процента и обратную косую черту во входной строке.

## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Примеры регулярных выражений](regex-examples.md)



<!--HONumber=Nov16_HO3-->


