---
title: "Creating Threads and Passing Data at Start Time | Microsoft Docs"
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
  - "threading [.NET Framework], creating"
  - "threading [.NET Framework], passing data to threads"
  - "threading [.NET Framework], retrieving data from threads"
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Creating Threads and Passing Data at Start Time
При создании процесса операционной системы в него включается поток вместе с исходным доменом приложения.  С этого момента домены приложения можно создавать и уничтожать, не создавая и не уничтожая потоки операционной системы.  Если выполняемый код является управляемым, объект <xref:System.Threading.Thread> для потока, выполняющегося в текущем домене приложения, может быть получен посредством статического свойства <xref:System.Threading.Thread.CurrentThread%2A> типа <xref:System.Threading.Thread>.  В этом разделе описывается создание потока, и обсуждаются альтернативные способы передачи данных в процедуру потока.  
  
## Создание потока  
 Создание нового объекта <xref:System.Threading.Thread> приводит к созданию нового управляемого потока.  Класс <xref:System.Threading.Thread> имеет конструкторы, которые принимают делегат <xref:System.Threading.ThreadStart> или делегат <xref:System.Threading.ParameterizedThreadStart>; этот делегат служит оболочкой для метода, который был вызван новым потоком при вызове пользователем метода <xref:System.Threading.Thread.Start%2A>.  Неоднократный вызов перегрузки <xref:System.Threading.Thread.Start%2A> приводит к созданию исключения <xref:System.Threading.ThreadStateException>.  
  
 Метод <xref:System.Threading.Thread.Start%2A> возвращается немедленно, как правило до фактического запуска нового потока.  Можно использовать свойства <xref:System.Threading.Thread.ThreadState%2A> и <xref:System.Threading.Thread.IsAlive%2A> для определения состояния потока в любой момент, однако эти свойства никогда не должны использоваться для синхронизации действий потоков.  
  
> [!NOTE]
>  Нет нужды в сохранении ссылки на объект <xref:System.Threading.Thread> после запуска потока.  Поток продолжает выполняться до завершения потоковой процедуры.  
  
 В следующем примере показано создание двух потоков с целью вызова статических методов и методов экземпляров для другого объекта.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## Передача данных в потоки и получение данных из потоков  
 В .NET Framework версии 2.0 делегат <xref:System.Threading.ParameterizedThreadStart> предоставляет простой способ передачи объекта, содержащего данные, в поток при вызове перегрузки метода <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>.  Пример кода см. в разделе <xref:System.Threading.ParameterizedThreadStart>.  
  
 Использование делегата <xref:System.Threading.ParameterizedThreadStart> не является типобезопасным способом передачи данных, так как перегрузка метода <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> принимает любой объект.  Альтернативой является инкапсуляция процедуры потока и данных во вспомогательном классе и использование делегата <xref:System.Threading.ThreadStart> для выполнения процедуры потока.  Этот подход показан в приведенных ниже двух примерах кода.  
  
 Ни один из этих делегатов не имеет возвращаемого значения, потому что отсутствует расположение для возвращения данных после асинхронного вызова.  Для получения результатов метода потока можно воспользоваться методом обратного вызова, как показано во втором примере.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### Получение данных с помощью метода обратного вызова  
 В следующем примере показана работа метода обратного вызова, с помощью которого получаются данные из потока.  Конструктор класса, содержащего данные и метод потока, также допускает использование делегата, предоставляющего метод обратного вызова; перед завершением работы метод потока вызывает делегат обратного вызова.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## См. также  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadStart>   
 <xref:System.Threading.ParameterizedThreadStart>   
 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)