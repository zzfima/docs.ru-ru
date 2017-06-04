---
title: "Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами | Microsoft Docs"
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
  - "анонимные каналы [платформа .NET Framework]"
  - "взаимодействие на локальном компьютере [платформа .NET Framework], каналы"
  - "одностороннее взаимодействие [платформа .NET Framework]"
  - "взаимодействие родительских объектов с дочерними [платформа .NET Framework]"
  - "каналы [платформа .NET Framework]"
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами
Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.  Они предоставляют меньше функциональных возможностей, чем именованные каналы, но и требуют меньших затрат ресурсов.  Можно использовать анонимные каналы для упрощения взаимодействия между процессами на локальном компьютере.  Нельзя использовать анонимные каналы для взаимодействия по сети.  
  
 Для реализации анонимных каналов используйте классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## Пример  
 В следующем примере показан способ отправки строки из родительского процесса в дочерний процесс с помощью анонимных каналов.  В этом примере создается объект <xref:System.IO.Pipes.AnonymousPipeServerStream> в рамках родительского процесса со значением <xref:System.IO.Pipes.PipeDirection> свойства <xref:System.IO.Pipes.PipeDirection>.  Родительский процесс затем создает дочерний процесс с помощью дескриптора клиента, чтобы создать объект <xref:System.IO.Pipes.AnonymousPipeClientStream>.  Дочерний процесс имеет значение <xref:System.IO.Pipes.PipeDirection> свойства <xref:System.IO.Pipes.PipeDirection>.  
  
 Родительский процесс затем передает пользовательскую строку дочернему процессу.  Строка отображается на консоли в дочернем процессе.  
  
 В следующем примере показан серверный процесс.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## Пример  
 В следующем примере показан клиентский процесс.  Серверный процесс запускает клиентский процесс и передает этому процессу дескриптор клиента.  Полученный из кода клиента исполняемый файл должен называться `pipeClient.exe` и должен быть скопирован в тот же каталог, что и исполняемый файл сервера перед запуском серверного процесса.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## См. также  
 [Каналы](../../../docs/standard/io/pipe-operations.md)   
 [Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)