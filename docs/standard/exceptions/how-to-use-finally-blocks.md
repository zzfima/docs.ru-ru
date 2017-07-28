---
title: "Практическое руководство. Использование блоков Finally | Microsoft Docs"
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
  - "ArgumentOutOfRangeException - класс"
  - "исключения, finally - блоки"
  - "исключения, блоки try/catch"
  - "finally - блоки"
  - "блоки try/catch"
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Использование блоков Finally
При возникновении исключения выполнение процессов останавливается, и управление передается ближайшему обработчику исключений.  Часто это означает, что не выполняются те строки кода, которые, как предполагается, всегда вызываются.  Очистка некоторых ресурсов, такая как закрытие файла, должна выполняться всегда, даже если создается исключение.  Для этого можно использовать блок finally.  Блок finally выполняется всегда, вне зависимости от возникновения исключения.  
  
 В следующем примере кода блок try\/catch используется для перехвата <xref:System.ArgumentOutOfRangeException>.  Метод `Main` создает два массива и пытается скопировать один из них в другой.  Это действие инициирует исключение **ArgumentOutOfRangeException**, и на консоль выводится сообщение об ошибке.  Блок finally выполняется вне зависимости от результата операции копирования.  
  
## Пример  
 [!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
 [!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
 [!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  
  
## См. также  
 [Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Практическое руководство. Явное создание исключения](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Практическое руководство. Создание пользовательских исключений](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)