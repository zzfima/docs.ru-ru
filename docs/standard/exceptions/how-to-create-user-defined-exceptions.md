---
title: "Практическое руководство. Создание пользовательских исключений | Microsoft Docs"
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
  - "исключения, примеры"
  - "исключения, определяемые пользователем"
  - "исключения, определенные пользователем"
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание пользовательских исключений
Необходимо предоставить пользователю возможность на программном уровне различать условия возникновения ряда ошибок, можно создать свои пользовательские исключения.  Платформа .NET Framework предоставляет иерархию классов исключений, производных от базового класса <xref:System.Exception>.  Каждый из этих классов самостоятельно определяет конкретное исключение, так что во многих случаях требуется только выполнить перехват этого исключения.  Также можно создавать собственные классы исключений, производные от класса <xref:System.Exception>.  
  
 При создании собственных исключений рекомендуется завершать имя класса пользовательского исключения словом "Exception". Также рекомендуется реализовать три общих конструктора, как показано в следующем примере.  
  
> [!NOTE]
>  В ситуациях, когда используется удаленное взаимодействие, необходимо гарантировать серверу \(вызываемый объект\) и клиенту \(прокси\-объект или вызывающий объект\) доступность метаданных для любого пользовательского исключения.  Например, код, вызывающий метод в отдельном домене приложения, должен иметь возможность найти сборку, содержащую исключение, созданное удаленным вызывающим объектом.  Дополнительные сведения см. в разделе [Наилучшие способы обработки исключений](../../../docs/standard/exceptions/best-practices-for-exceptions.md).  
  
 В следующем примере новый класс исключений `EmployeeListNotFoundException` является производным от <xref:System.Exception>.  В этом классе определены три конструктора, принимающие различные параметры.  
  
## Пример  
 [!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
 [!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
 [!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  
  
## См. также  
 [Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Практическое руководство. Использование определенных исключений в блоке Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Лучшие методики обработки исключений](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)