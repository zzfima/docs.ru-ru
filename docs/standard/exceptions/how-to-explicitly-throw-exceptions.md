---
title: "Практическое руководство. Явное создание исключения | Microsoft Docs"
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
  - "исключения, создание"
  - "исключения, блоки try/catch"
  - "FileNotFoundException - класс"
  - "неявное создание исключений"
  - "блоки try/catch"
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Явное создание исключения
Исключения можно создавать явно с помощью оператора `throw`.  Используя оператор `throw`, также можно переслать далее перехваченное исключение.  Хорошей практикой в программировании является добавление информации к исключению, которое посылается повторно — это позволяет сделать процесс отладки более информативным.  
  
 В следующем примере кода для перехвата возможного исключения <xref:System.IO.FileNotFoundException> используется блок try\/catch.  За блоком try следует блок catch, который перехватывает исключение <xref:System.IO.FileNotFoundException>и выводит на консоль сообщение в том случае, если файл данных не найден.  Далее идет оператор throw, который создает новое исключение <xref:System.IO.FileNotFoundException> и добавляет к исключению текстовую информацию.  
  
## Пример  
 [!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
 [!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  
  
## См. также  
 [Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Практическое руководство. Использование определенных исключений в блоке Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Практическое руководство. Использование блоков Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)