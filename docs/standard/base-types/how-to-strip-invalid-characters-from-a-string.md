---
title: "Практическое руководство. Исключение недопустимых символов из строки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "регулярные выражения, примеры"
  - "очистка ввода"
  - "ввод пользователя, примеры"
  - "регулярные выражения .NET Framework, примеры"
  - "регулярные выражения [платформа .NET Framework], примеры"
  - "Regex.Replace - метод"
  - "удаление недопустимых знаков"
  - "Replace - метод"
  - "проверка пользовательского ввода"
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Исключение недопустимых символов из строки
В следующем примере используется статический метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> для исключения недопустимых символов из строки.  
  
## Пример  
 Определенный в этом примере метод `CleanInput` используется для удаления потенциально опасных символов, введенных в текстовое поле пользователем.  В данном случае `CleanInput` возвращает строку после удаления всех знаков, не являющихся буквенно\-цифровыми, за исключением символов "@", "\-" \(дефис\) и "." \(точки\).  Однако шаблон регулярного выражения можно изменить таким образом, чтобы исключались все символы, которые не должны входить во входную строку.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 Шаблон регулярного выражения `[^\w\.@-]` ищет совпадения для всех символов, которые не являются алфавитно\-цифровым знаком, символом "@", "\-" \(дефис\).  Символ слова — это любая буква, десятичная цифра или любой соединительный знак пунктуации \(например, символ подчеркивания\).  Все символы, которые совпадают с данным шаблоном заменяются строкой <xref:System.String.Empty?displayProperty=fullName>, которая является строкой, заданной в шаблоне замены.  Чтобы разрешить дополнительные символы во входной строке, добавьте эти символы в класс символов в шаблоне регулярного выражения.  Например, шаблон регулярного выражения `[^\w\.@-\\%]` также разрешает знак процента и обратную косую черту во входной строке.  
  
## См. также  
 [Регулярные выражения в .NET Framework](../../../docs/standard/base-types/regular-expressions.md)