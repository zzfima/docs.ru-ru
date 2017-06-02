---
title: "Практическое руководство. Выполнение базовых операций со строками в .NET Framework | Microsoft Docs"
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
  - "строки [платформа .NET Framework], примеры"
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Выполнение базовых операций со строками в .NET Framework
В следующем примере некоторые методы, описанные в разделе [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении.  Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю.  Более того, данный класс позволяет пользователю вводить сведения о городе, области и почтовом индексе в одну строку. Приложение автоматически разбирает эту строку и вводит необходимые сведения в соответствующее свойство.  
  
 В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.  
  
## Пример  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес.  Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.  
  
## См. также  
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)