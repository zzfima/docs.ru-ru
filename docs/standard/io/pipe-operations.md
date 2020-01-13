---
title: Операции с каналами в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 693dd1eb0b0b9bb87973eead26a344ed67641e34
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706560"
---
# <a name="pipe-operations-in-net"></a>Операции с каналами в .NET
Каналы предоставляют средства для межпроцессного взаимодействия. Существует два типа каналов.  
  
- Анонимные каналы.  
  
     Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере. Анонимные каналы требуют меньше ресурсов, чем именованные каналы, но предоставляют меньше возможностей. Анонимные каналы являются односторонними и их нельзя использовать в сети. Они поддерживают только один экземпляр сервера. Анонимные каналы подходят для взаимодействия между потоками или между родительским и дочерним процессами, поскольку в этих сценариях дескриптор канала можно легко передать дочернему процессу при его создании.  
  
     В .NET анонимные каналы реализуются с помощью классов <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     См. практическое руководство по [ Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Именованные каналы.  
  
     Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала. Именованные каналы могут быть односторонним или дуплексным. Они поддерживают связь на основе сообщений и позволяют нескольким клиентам одновременно подключаться к одному серверному процессу через канал с тем же именем. Именованные каналы также поддерживают олицетворение, при котором подключенные процессы используют на удаленных серверах собственные разрешения доступа.  
  
     В .NET именованные каналы реализуются с помощью классов <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     См. практическое руководство по [ Использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>См. также

- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
- [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
