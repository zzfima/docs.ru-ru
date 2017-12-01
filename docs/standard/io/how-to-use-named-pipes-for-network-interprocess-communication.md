---
title: "Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети"
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
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети
Именованные каналы обеспечивают межпроцессное взаимодействие между сервером и одной или несколькими клиентами. Они предоставляют больше функциональных возможностей, чем анонимные каналы, которые обеспечивают межпроцессное взаимодействие на локальном компьютере. Именованные каналы поддерживают полную дуплексную связь по сети и несколько экземпляров сервера, связь на основе сообщений и олицетворение клиента, позволяющее подключающимся процессам использовать собственные наборы разрешений на удаленных серверах.  
  
 Для реализации именованных каналов используются классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание именованного канала с помощью <xref:System.IO.Pipes.NamedPipeServerStream> класса. В этом примере серверный процесс создает четыре потока. Каждый поток может принимать подключения клиента. Процесс подключенный клиент предоставляет сервера с именем файла. Если клиент имеет достаточные разрешения, серверный процесс открывает файл и отправляет его содержимое обратно клиенту.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано клиентского процесса, который использует <xref:System.IO.Pipes.NamedPipeClientStream> класса. Клиент подключается к серверному процессу и отправляет имя файла на сервер. В примере используется олицетворение, поэтому удостоверение, на котором работает клиентское приложение должно иметь разрешение на доступ к файлу. Затем сервер отправляет содержимое файла обратно клиенту. Затем содержимое файла отображаются на консоль.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Клиентские и серверные процессы в этом примере предназначены для запуска на том же компьютере, поэтому предоставленное имя сервера для <xref:System.IO.Pipes.NamedPipeClientStream> объект `"."`. Если клиентские и серверные процессы выполнялись на разных компьютерах, `"."` должно было быть заменено сетевое имя компьютера, на котором запускает серверный процесс.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [Каналы](../../../docs/standard/io/pipe-operations.md)  
 [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
