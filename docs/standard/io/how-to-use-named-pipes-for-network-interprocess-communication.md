---
title: "Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети | Microsoft Docs"
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
  - "связь с полным дуплексом [платформа .NET Framework], именованные каналы"
  - "олицетворение [платформа .NET Framework], именованные каналы"
  - "связь на основе сообщений [платформа .NET Framework], именованные каналы"
  - "несколько подключений через именованные каналы"
  - "именованные каналы [платформа .NET Framework]"
  - "сетевые взаимодействия [платформа .NET Framework], именованные каналы"
  - "каналы [платформа .NET Framework]"
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети
Именованные каналы обеспечивают межпроцессное взаимодействие между сервером и одним или несколькими клиентами.  Они предоставляют больше функциональных возможностей, чем анонимные каналы, которые обеспечивают межпроцессное взаимодействие на локальном компьютере.  Именованные каналы поддерживают полную дуплексную связь по сети и множество экземпляров сервера; связь на основе сообщений; выполнение роли клиента, позволяющее подключающимся процессам использовать свои собственные наборы разрешений на удаленных серверах.  
  
 Для реализации именованных каналов используйте классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## Пример  
 В следующем примере демонстрируется создание именованного канала с помощью класса <xref:System.IO.Pipes.NamedPipeServerStream>.  В этом примере обслуживающий процесс в сети создает четыре потока.  Каждый поток может принять обслуживаемый процесс.  Подключенный обслуживаемый процесс предоставляет имя файла серверу.  Если клиент имеет достаточные разрешения, то обслуживающий серверный процесс открывает файл и отправляет его содержимое обратно клиенту.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## Пример  
 В следующем примере показан обслуживаемый клиентский процесс, который использует класс <xref:System.IO.Pipes.NamedPipeClientStream>.  Клиент подключается к обслуживающему серверному процессу и отправляет имя файла серверу.  В примере используется олицетворение, поэтому удостоверение, запускающее клиентское приложение, должно иметь разрешение на доступ к файлу.  Затем сервер отправляет содержимое файла обратно клиенту.  Затем содержимое файла отображается на консоли.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## Отказоустойчивость  
 Клиентские и серверные процессы в этом примере предназначены для запуска на одном и том же компьютере, поэтому предоставленное имя сервера для объекта <xref:System.IO.Pipes.NamedPipeClientStream> является `"."`.  Если бы клиентские и серверные процессы выполнялись на разных компьютерах, то имя `"."` должно было быть заменено сетевым именем компьютера, который запускает серверный процесс.  
  
## См. также  
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>   
 [Каналы](../../../docs/standard/io/pipe-operations.md)   
 [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)