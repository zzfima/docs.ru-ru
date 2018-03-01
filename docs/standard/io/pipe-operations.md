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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68c1ad34952ee4d20dbf56aa8ca437a3f99db751
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Операции с каналами в .NET Framework
Каналы предоставляют средства для межпроцессного взаимодействия. Существует два типа каналов.  
  
-   Анонимные каналы.  
  
     Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере. Анонимные каналы требуют меньше ресурсов, чем именованные каналы, но предоставляют меньше возможностей. Анонимные каналы являются односторонними и их нельзя использовать в сети. Они поддерживают только один экземпляр сервера. Анонимные каналы подходят для взаимодействия между потоками или между родительским и дочерним процессами, поскольку в этих сценариях дескриптор канала можно легко передать дочернему процессу при его создании.  
  
     На платформе .NET Framework анонимные каналы реализуются через классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     Дополнительные сведения см. в статье [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Именованные каналы.  
  
     Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала. Именованные каналы могут быть односторонним или дуплексным. Они поддерживают связь на основе сообщений и позволяют нескольким клиентам одновременно подключаться к одному серверному процессу через канал с тем же именем. Именованные каналы также поддерживают олицетворение, при котором подключенные процессы используют на удаленных серверах собственные разрешения доступа.  
  
     На платформе .NET Framework именованные каналы реализуются через классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     Дополнительные сведения см. в статье [Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)  
 [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
