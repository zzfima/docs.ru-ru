---
title: Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706638"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами
Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала. Они предоставляют больше функциональных возможностей, чем анонимные каналы, которые обеспечивают межпроцессное взаимодействие на локальном компьютере. Именованные каналы поддерживают полную дуплексную связь по сети и несколько экземпляров сервера, связь на основе сообщений и олицетворение клиента, позволяющее подключающимся процессам использовать собственные наборы разрешений на удаленных серверах.  
  
 Для реализации именованных каналов используются классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## <a name="example"></a>Пример  
 В примере ниже показано, как создать именованный канал с помощью класса <xref:System.IO.Pipes.NamedPipeServerStream>. В этом примере серверный процесс создает четыре потока. Каждый поток может принимать подключение клиента. Процесс подключения клиента передает серверу имя файла. Если клиенту имеет необходимые разрешения, серверный процесс открывает указанный файл и отправляет клиенту его содержимое.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>Пример  
 В примере ниже представлен клиентский процесс, основанный на классе <xref:System.IO.Pipes.NamedPipeClientStream>. Клиент подключается к серверному процессу и передает серверу имя файла. В этом примере используется олицетворение. Это означает, что у идентификатора, от имени которого выполняется клиентское приложение, должны быть разрешения на доступ к файлу. Затем сервер отправляет клиенту содержимое файла. Полученное содержимое файла выводится в консоль.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Клиентский и серверный процессы в этом примере предназначены для выполнения на одном компьютере, поэтому объекту <xref:System.IO.Pipes.NamedPipeClientStream> передается имя сервера `"."`. Если клиентский и серверный процессы выполняются на разных компьютерах, вместо `"."` должно быть указано сетевое имя компьютера, на котором осуществляется серверный процесс.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [Каналы](../../../docs/standard/io/pipe-operations.md)
- [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
