---
title: "Таблица форматирования числовых результатов (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "форматирование [C#]"
  - "числовое форматирование [C#]"
  - "String.Format - метод"
  - "Console.Write - метод"
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Таблица форматирования числовых результатов (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для форматирования числовых результатов можно использовать метод <xref:System.String.Format%2A?displayProperty=fullName>, а также метод <xref:System.Console.Write%2A?displayProperty=fullName> или <xref:System.Console.WriteLine%2A?displayProperty=fullName>, который вызывает метод `String.Format`.  Формат задается с помощью строк формата.  В следующей таблице приведены поддерживаемые строки стандартных форматов.  Строка формата принимает следующую форму: `Axx`, где `A` — описатель формата, а `xx` — описатель точности.  Описатель формата управляет типом форматирования, применяемым к числовому значению, а описатель точности управляет количеством значащих цифр или десятичных знаков форматированного результата.  Значение описатель точности в диапазоне от 0 до 99.  
  
 Дополнительные сведения о стандартных и пользовательских строках формата см. в разделе [Типы форматирования](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.  
  
|Описатель формата|Описание|Примеры|Output|  
|-----------------------|--------------|-------------|------------|  
|C или c|Валюта|Console.Write\("{0:C}", 2.5\);<br /><br /> Console.Write\("{0:C}", \-2.5\);|$2.50<br /><br /> \($2.50\)|  
|D или d|Decimal|Console.Write\("{0:D5}", 25\);|00025|  
|E или e|Научный формат|Console.Write\("{0:E}", 250000\);|2.500000E\+005|  
|F или f|Фиксированная запятая|Console.Write\("{0:F2}", 25\);<br /><br /> Console.Write\("{0:F0}", 25\);|25.00<br /><br /> 25|  
|G или g|Общие|Console.Write\("{0:G}", 2.5\);|2.5|  
|N или n|Number|Console.Write\("{0:N}", 2500000\);|2,500,000.00|  
|X или x|Шестнадцатеричный|Console.Write\("{0:X}", 250\);<br /><br /> Console.Write\("{0:X}", 0xffff\);|FA<br /><br /> FFFF|  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Строки стандартных числовых форматов](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [string](../../../csharp/language-reference/keywords/string.md)