---
title: "Операции с каналами в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Операции с каналами в .NET Framework
Каналы предоставляют средства для межпроцессного взаимодействия. Существует два типа каналов:  
  
-   Анонимные каналы.  
  
     Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере. Анонимные каналы требует меньше ресурсов, чем именованные каналы, но возможности ограничены. Анонимные каналы являются односторонними и не может использоваться в сети. Они поддерживают только один экземпляр сервера. Анонимные каналы полезны для взаимодействия между потоками или между родительским и дочерним процессами, где дескриптор канала можно легко передать дочернему процессу при его создании.  
  
     В платформе .NET Framework с помощью реализации анонимных каналов <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream> классы.  
  
     В разделе [как: использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Именованные каналы.  
  
     Именованные каналы обеспечивают межпроцессное взаимодействие между сервером и одной или несколькими клиентами. Именованные каналы могут быть односторонним или дуплексным. Они поддерживают связь на основе сообщений и разрешить нескольким клиентам одновременно подключаться к серверному процессу, используя то же имя канала. Именованные каналы также поддерживают олицетворение, позволяющее подключающимся процессам использовать собственные разрешения на удаленных серверах.  
  
     В .NET Framework, именованные каналы реализуются с помощью <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream> классы.  
  
     В разделе [как: использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)  
 [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
