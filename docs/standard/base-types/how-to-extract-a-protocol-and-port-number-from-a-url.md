---
title: "Практическое руководство. Извлечение протокола и номера порта из URL-адреса | Microsoft Docs"
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
  - "регулярные выражения .NET Framework, примеры"
  - "разбор текста с регулярными выражениями, примеры"
  - "синтаксис соответствия шаблону с регулярными выражениями, примеры"
  - "регулярные выражения [платформа .NET Framework], примеры"
  - "регулярные выражения, примеры"
  - "поиск с регулярными выражениями, примеры"
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Извлечение протокола и номера порта из URL-адреса
В следующем примере выполняется извлечение протокола и номера порта из URL\-адреса.  
  
## Пример  
 В примере используется метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> для возврата протокола, за которым через двоеточие следует номер порта.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.  
  
|Шаблон|Описание|  
|------------|--------------|  
|`^`|Соответствие должно обнаруживаться в начале строки.|  
|`(?<proto>\w+)`|Совпадение с одним или несколькими символами слова.  Эта группа должна получить имя `proto`.|  
|`://`|Соответствует двоеточию, за которым следуют две косые черты.|  
|`[^/]+?`|Соответствует одному или нескольким вхождениям \(но как можно меньшему числу\) любого символа, отличного от косой черты.|  
|`(?<port>:\d+)?`|Соответствует вхождениям в количестве 0 или 1 двоеточия, за которым следует одна или несколько цифр.  Эта группа должна получить имя `port`.|  
|`/`|Соответствует косой черте.|  
  
 Метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> разворачивает последовательность замены `${proto}${port}`, которая объединяет захваченное значение двух именованных групп в шаблон регулярного выражения.  Это удобная альтернатива явному объединению строк, извлеченных из объекта коллекции, который был возвращен свойством <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=fullName>.  
  
 В следующем примере используется метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> с двумя подстановками, `${proto}` и`${port}`, для включения захваченных групп в выходную строку.  Вместо этого, можно извлечь захваченные группы из соответствующего объекта <xref:System.Text.RegularExpressions.GroupCollection>, как показано в следующем примере кода.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## См. также  
 [Регулярные выражения в .NET Framework](../../../docs/standard/base-types/regular-expressions.md)