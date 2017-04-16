---
title: "Пример регулярного выражения. Изменение форматов даты | Microsoft Docs"
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
  - "поиск с использованием регулярных выражений, примеры"
  - "разбор текста с использованием регулярных выражений, примеры"
  - "регулярные выражения, примеры"
  - "регулярные выражения .NET Framework, примеры"
  - "регулярные выражения [платформа .NET Framework], примеры"
  - "синтаксис соответствия шаблону с регулярными выражениями, примеры"
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Пример регулярного выражения. Изменение форматов даты
В следующем примере кода метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> используется для замены дат, которые имеют форму *mm*\/*dd*\/*yy* на даты, которые имеют форму *dd*\-*mm*\-*yy*.  
  
## Пример  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 В следующем коде показано, как метод `MDYToDMY` можно вызвать в приложении.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## Комментарии  
 Интерпретация шаблона регулярного выражения `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` показана в следующей таблице.  
  
|Шаблон|Описание|  
|------------|--------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`(?<month>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами.  Это записанная группа `month`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<day>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами.  Это записанная группа `day`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<year>\d{2,4})`|Совпадение двумя–четырьмя десятичными цифрами.  Это записанная группа `year`.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  
  
 Шаблон `${day}-${month}-${year}` задает строку замены, которая представлена в следующей таблице.  
  
|Шаблон|Описание|  
|------------|--------------|  
|`$(day)`|Добавляет строку, которая записана группой записи `day`.|  
|`-`|Добавляет знак дефиса.|  
|`$(month)`|Добавляет строку, которая записана группой записи `month`.|  
|`-`|Добавляет знак дефиса.|  
|`$(year)`|Добавляет строку, которая записана группой записи `year`.|  
  
## См. также  
 [Регулярные выражения в .NET Framework](../../../docs/standard/base-types/regular-expressions.md)