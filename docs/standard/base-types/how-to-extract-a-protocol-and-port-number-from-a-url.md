---
title: "Практическое руководство. Извлечение протокола и номера порта из URL-адреса"
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Практическое руководство. Извлечение протокола и номера порта из URL-адреса
В следующем примере выполняется извлечение протокола и номера порта из URL-адреса.  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> метод для возврата протокола и двоеточие, за которым следует номер порта.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`^`|Соответствие должно обнаруживаться в начале строки.|  
|`(?<proto>\w+)`|Совпадение с одним или несколькими символами слова. Имя этой группы `proto`.|  
|`://`|Совпадение с двоеточием, за которым следуют две косые черты.|  
|`[^/]+?`|Совпадение с одним или несколькими вхождениями (но как можно меньшему числу) любого символа, отличного от косой черты.|  
|`(?<port>:\d+)?`|Совпадение с вхождениями в количестве 0 или 1 двоеточия, за которым следует одна или несколько цифр. Имя этой группы `port`.|  
|`/`|Совпадение с косой чертой.|  
  
 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Метод развертывает `${proto}${port}` замены последовательности, который объединяет значение две именованные группы, в шаблоне регулярного выражения. Он является удобной альтернативой явно сцепления строк, полученных из коллекции объект, возвращаемый <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> свойство.  
  
 В этом примере <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> метод с двумя подстановками `${proto}` и `${port}`, включаемых в выходной строке записанной группы. Захватываемым группам можно получить из соответствующего <xref:System.Text.RegularExpressions.GroupCollection> вместо этого, как показано в следующем коде.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
