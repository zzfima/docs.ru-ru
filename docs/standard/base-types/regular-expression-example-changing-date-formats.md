---
title: "Пример регулярного выражения. Изменение форматов даты"
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
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 93c526e87f7aba650cce397962c7262b6fd2f085
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="regular-expression-example-changing-date-formats"></a>Пример регулярного выражения. Изменение форматов даты
В следующем примере кода метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> используется для замены дат в формате *мм*/*дд*/*гг* на даты в формате *дд*-*мм*-*гг*.  
  
## <a name="example"></a>Пример  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 В следующем коде показано, как можно вызывать метод `MDYToDMY` в приложении.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a>Комментарии  
 Возможные интерпретации шаблона регулярного выражения `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`(?<month>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами. Это записанная группа `month`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<day>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами. Это записанная группа `day`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<year>\d{2,4})`|Совпадение с двумя-четырьмя десятичными цифрами. Это записанная группа `year`.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  
  
 Шаблон `${day}-${month}-${year}` определяет строку замены, как показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`$(day)`|Добавляет строку, которая записана захватываемой группой `day`.|  
|`-`|Добавляет символ дефиса.|  
|`$(month)`|Добавляет строку, которая записана захватываемой группой `month`.|  
|`-`|Добавляет символ дефиса.|  
|`$(year)`|Добавляет строку, которая записана захватываемой группой `year`.|  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
