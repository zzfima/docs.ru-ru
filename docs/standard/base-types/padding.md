---
title: "Заполнение строк в .NET"
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
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a>Заполнение строк в .NET
Используйте один из следующих <xref:System.String> методы для создания новой строки, состоящий из исходной строки, дополняется стоящими в начале и конце строки символов в указанной общей длины. В качестве заполняющего знака, который, соответственно, будет повторяться либо справа, либо слева, может использоваться пробел или знак, заданный в явной форме.  
  
|Имя метода|Применение|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Дополняет строку до указанной общей длины знаками с начала.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Дополняет строку до указанной общей длины знаками с конца.|  
  
## <a name="padleft"></a>PadLeft  
 <xref:System.String.PadLeft%2A?displayProperty=nameWithType> Метод создает новую строку с помощью объединения знаки к исходной строке, для достижения указанной общей длины. <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> Метод использует в качестве символа заполнения пустого пространства и <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> метод дает возможность указать собственные заполняющий символ.  
  
 Следующий пример кода использует <xref:System.String.PadLeft%2A> метод для создания новой строки, длину 20 символов. Этот пример выводит на консоль значение "`--------Hello World!`".  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 <xref:System.String.PadRight%2A?displayProperty=nameWithType> Метод создает новую строку с помощью объединения знаки к исходной строке, для достижения указанной общей длины. <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> Метод использует в качестве символа заполнения пустого пространства и <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> метод дает возможность указать собственные заполняющий символ.  
  
 Следующий пример кода использует <xref:System.String.PadRight%2A> метод для создания новой строки, длину 20 символов. Этот пример выводит на консоль значение "`Hello World!--------`".  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
