---
title: "Создание потоков и передача данных во время запуска"
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
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Создание потоков и передача данных во время запуска
При создании процесса операционной системы, операционная система включается поток для выполнения кода в этом процессе, включая исходным доменом приложения. С этого момента домены приложений могут создаваться и уничтожаться, без каких-либо потоков операционной системы, обязательно создается или уничтожается. Если выполняемый код является управляемым кодом, то <xref:System.Threading.Thread> объекта для потока, выполняющегося в текущем домене приложения можно получить посредством статического <xref:System.Threading.Thread.CurrentThread%2A> свойство типа <xref:System.Threading.Thread>. В этом разделе описывается создание потока и обсуждаются альтернативные способы передачи данных в процедуру потока.  
  
## <a name="creating-a-thread"></a>Создание потока  
 Создание нового <xref:System.Threading.Thread> объект создает нового управляемого потока. <xref:System.Threading.Thread> Класс имеет конструкторы, принимающие <xref:System.Threading.ThreadStart> делегата или <xref:System.Threading.ParameterizedThreadStart> делегата; делегат инкапсулирует метод, который может быть вызван с новым потоком при вызове <xref:System.Threading.Thread.Start%2A> метода. Вызов <xref:System.Threading.Thread.Start%2A> несколько раз вызывает <xref:System.Threading.ThreadStateException> исключение.  
  
 <xref:System.Threading.Thread.Start%2A> Метод возвращается немедленно, часто до действительно был запущен новый поток. Можно использовать <xref:System.Threading.Thread.ThreadState%2A> и <xref:System.Threading.Thread.IsAlive%2A> свойства, чтобы определить состояние потока в настоящий момент, но эти свойства никогда не должен использоваться для синхронизации действий потоков.  
  
> [!NOTE]
>  После запуска потока, нет необходимости сохранять ссылку на <xref:System.Threading.Thread> объекта. Поток продолжает выполняться до завершения потоковой процедуры.  
  
 В следующем примере кода создается два новых потоков для вызова экземпляра и статические методы в другой объект.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a>Передача данных в потоки и получение данных из потоков  
 В .NET Framework версии 2.0 <xref:System.Threading.ParameterizedThreadStart> делегат предоставляет простой способ передачи объекта, содержащего данные в поток при вызове <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> перегрузки метода. См. пример кода в <xref:System.Threading.ParameterizedThreadStart>.  
  
 С помощью <xref:System.Threading.ParameterizedThreadStart> делегат несовместим типобезопасный способ передачи данных, так как <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> перегруженный метод принимает любой объект. Альтернативой является инкапсуляция процедуры потока и данных во вспомогательном классе и использование <xref:System.Threading.ThreadStart> делегат для выполнения процедуры потока. Этот способ показан в приведенных ниже примерах кода.  
  
 Ни один из этих делегатов не имеет возвращаемого значения, поскольку нет места для возвращения данных после асинхронного вызова. Для получения результатов метода потока, можно использовать метод обратного вызова, как показано во втором примере кода.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a>Извлечение данных с помощью методов обратного вызова  
 В следующем примере показано, метод обратного вызова, который получает данные из потока. Конструктор для класса, содержащего данные и метод потока также принимает делегат, представляющий метод обратного вызова; Перед завершением работы метод потока, он вызывает делегат обратного вызова.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
