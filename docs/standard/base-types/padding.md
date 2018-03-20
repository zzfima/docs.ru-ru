---
title: "Заполнение строк в .NET"
ms.custom: 
ms.date: 03/15/2018
ms.prod: .net
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
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bf90c841c8fff21dd423fcd19613b5eb46a2c80c
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="padding-strings-in-net"></a>Заполнение строк в .NET

Перечисленные ниже методы класса <xref:System.String> позволяют создать новую строку, состоящей из исходной строки, и дополнить ее указанными символами с начала или с конца до указанной общей длины. Символом заполнения может быть пробел или указанный знак. Итоговая строка выравнивается по правому или левому краю. Если длина исходной строки уже больше или равна требуемой общей длины, методы заполнения возвращают исходную строку без изменений. Дополнительные сведения см. в разделах **Возвращаемые значения** описания двух перегрузок методов <xref:System.String.PadLeft%2A?displayProperty=nameWithType> и <xref:System.String.PadRight%2A?displayProperty=nameWithType>.
  
|Имя метода|Использовать|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Дополняет строку до указанной общей длины знаками с начала.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Дополняет строку до указанной общей длины знаками с конца.|  
  
## <a name="padleft"></a>PadLeft  
 Метод <xref:System.String.PadLeft%2A?displayProperty=nameWithType> создает новую строку, присоединяя в начало исходной строки заполняющие символы в количестве, необходимом для достижения указанной общей длины. Метод <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> в качестве заполняющих символов использует пробелы, а метод <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> позволяет задать любой заполняющий символ.  
  
 В следующем примере кода метод <xref:System.String.PadLeft%2A>используется для создания новой строки длиной в двадцать символов. Этот пример выводит на консоль значение "`--------Hello World!`".  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 Метод <xref:System.String.PadRight%2A?displayProperty=nameWithType> создает новую строку, присоединяя в конец исходной строки заполняющие символы в количестве, необходимом для достижения указанной общей длины. Метод <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> в качестве заполняющих символов использует пробелы, а метод <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> позволяет задать любой заполняющий символ.  
  
 В следующем примере кода метод <xref:System.String.PadRight%2A>используется для создания новой строки длиной в двадцать символов. Этот пример выводит на консоль значение "`Hello World!--------`".  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
