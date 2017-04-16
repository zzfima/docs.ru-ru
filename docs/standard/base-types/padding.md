---
title: "Заполнение строк в .NET Framework | Microsoft Docs"
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
  - "заполнение строк"
  - "PadLeft - метод"
  - "PadRight - метод"
  - "строки [платформа .NET Framework], заполнение"
  - "пробел"
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Заполнение строк в .NET Framework
Для создания новой строки, состоящей из исходной строки, дополненной знаками до указанной общей длины с начала или с конца, следует использовать один из следующих методов класса <xref:System.String>.  В качестве заполняющего знака, который, соответственно, будет повторяться либо справа, либо слева, может использоваться пробел или знак, заданный в явной форме.  
  
|Название метода|Применение|  
|---------------------|----------------|  
|<xref:System.String.PadLeft%2A?displayProperty=fullName>|Дополняет строку до указанной общей длины знаками с начала.|  
|<xref:System.String.PadRight%2A?displayProperty=fullName>|Дополняет строку до указанной общей длины знаками с конца.|  
  
## PadLeft  
 Метод <xref:System.String.PadLeft%2A?displayProperty=fullName> создает новую строку, присоединяя к исходной строке знаки с начала в количестве, необходимом для достижения указанной общей длины.  В методе <xref:System.String.PadLeft%28System.Int32%29?displayProperty=fullName> в качестве заполняющих знаков используются пробелы, а метод <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=fullName> позволяет задать заполняющий знак в явной форме.  
  
 В следующем примере кода метод <xref:System.String.PadLeft%2A> используется для создания новой строки длиной в двадцать знаков.  Этот пример выводит на консоль текст "`--------Hello World!`".  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## PadRight  
 Метод <xref:System.String.PadRight%2A?displayProperty=fullName> создает новую строку, присоединяя к исходной строке знаки с конца в количестве, необходимом для достижения указанной общей длины.  В методе <xref:System.String.PadRight%28System.Int32%29?displayProperty=fullName> в качестве заполняющих знаков используются пробелы, а метод <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=fullName> позволяет задать заполняющий знак в явной форме.  
  
 В следующем примере кода метод <xref:System.String.PadRight%2A> используется для создания новой строки длиной в двадцать знаков.  Этот пример выводит на консоль текст "`Hello World!--------`".  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## См. также  
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)