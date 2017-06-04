---
title: "Практическое руководство. Использование определенных исключений в блоке Catch | Microsoft Docs"
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
  - "catch - блоки"
  - "исключения, блоки try/catch"
  - "блоки try/catch"
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Использование определенных исключений в блоке Catch
При возникновении исключения, оно передается в стек и каждый блок Catch рассматривает возможность его обработки.  Важен порядок операторов Catch.  Размещайте блоки Catch, предназначенные для определенных исключений, до главного блока Catch исключений, в противном случае, компилятор может выдать ошибку.  Соответствующий блок Catch определяется путем согласования типа исключения с именем исключения, указанным в этом блоке.  Если нет специальных блоков Catch, то исключение перехватывается главным блоком Catch, если он существует.  
  
 В следующем примере кода блок try\/catch используется для перехвата <xref:System.InvalidCastException>.  В примере создается класс с именем `Employee` с единственным свойством — уровень сотрудника \(`Emlevel`\).  Метод `, PromoteEmployee`, принимает объект и повышает уровень сотрудника.  Исключение **InvalidCastException** возникает, когда экземпляр <xref:System.DateTime> передается методу `PromoteEmployee`.  
  
## Пример  
 [!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
 [!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
 [!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]  
  
 Среда CLR перехватывает исключения, которые не перехватываются блоком Catch.  В зависимости от того, как настроена среда выполнения, появляется диалоговое окно отладки или выполнение программы прекращается и отображается диалоговое окно, содержащее сведения об исключении.  Дополнительные сведения об отладке см. в разделе [Отладка и профилирование приложений](../../../docs/framework/debug-trace-profile/index.md).  
  
## См. также  
 [Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Практическое руководство. Явное создание исключения](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Практическое руководство. Создание пользовательских исключений](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Практическое руководство. Использование блоков Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Класс Exception и его свойства](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)