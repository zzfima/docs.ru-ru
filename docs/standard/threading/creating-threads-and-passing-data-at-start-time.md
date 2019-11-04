---
title: Создание потоков и передача данных во время запуска
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138105"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Создание потоков и передача данных во время запуска

При создании процесса в операционной системе она добавляет поток для выполнения кода этого процесса, включая все исходные домены приложений. С этого момента домены приложений могут создаваться и уничтожаться, что не обязательно сопровождается созданием или уничтожением потоков операционной системы. Если выполняемый код является управляемым, то вы можете получить объект <xref:System.Threading.Thread> для потока, выполняющегося в текущем домене приложения. Для этого получите статическое свойство <xref:System.Threading.Thread.CurrentThread%2A> типа <xref:System.Threading.Thread>. В этой статье описано создание потока и несколько способов передачи данных в процедуру потока.  
  
## <a name="creating-a-thread"></a>Создание потока

 Создание нового объекта <xref:System.Threading.Thread> приводит к созданию нового управляемого потока. Класс <xref:System.Threading.Thread> имеет конструкторы, которые принимают делегат <xref:System.Threading.ThreadStart> или <xref:System.Threading.ParameterizedThreadStart>. Этот делегат инкапсулирует метод, который вызывается новым потоком при вызове метода <xref:System.Threading.Thread.Start%2A>. Повторный вызов <xref:System.Threading.Thread.Start%2A> приводит к созданию исключения <xref:System.Threading.ThreadStateException>.  
  
 Метод <xref:System.Threading.Thread.Start%2A> завершается немедленно, часто даже до запуска нового потока. Вы можете использовать свойства <xref:System.Threading.Thread.ThreadState%2A> и <xref:System.Threading.Thread.IsAlive%2A>, чтобы определить состояние потока в настоящий момент, но эти свойства ни в коем случае нельзя использовать для синхронизации действий потоков.  
  
> [!NOTE]
> После запуска потока не нужно сохранять ссылку на объект <xref:System.Threading.Thread>. Поток продолжит выполняться, пока не завершится запущенная в нем процедура.  
  
 В следующем примере кода создается два новых потока для вызова метода экземпляра и статического метода из другого объекта.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a>Передача данных в потоки

 На платформе .NET Framework версии 2.0 делегат <xref:System.Threading.ParameterizedThreadStart> предоставляет простой способ передать в поток объект с данными при вызове перегрузки метода <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>. См. пример кода в <xref:System.Threading.ParameterizedThreadStart>.  
  
 Делегат <xref:System.Threading.ParameterizedThreadStart> не является типобезопасным способом передачи данных, так как перегруженный метод <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> принимает любой объект. Вместо этого можно инкапсулировать процедуру потока и данные во вспомогательный класс и выполнять процедуру потока при помощи делегата <xref:System.Threading.ThreadStart>. В следующем примере показана эта техника.

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

Ни один из делегатов <xref:System.Threading.ThreadStart> или <xref:System.Threading.ParameterizedThreadStart> не имеет возвращаемого значения, так как им некуда возвращать данные после асинхронного вызова. Чтобы получить результаты из метода потока, вы можете использовать метод обратного вызова, как показано в следующем разделе.
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a>Извлечение данных из потоков с помощью методов обратного вызова

 Приведенный ниже пример демонстрирует метод обратного вызова, который получает данные из потока. Конструктор класса, содержащего данные и метод потока, также принимает делегат, который представляет метод обратного вызова. Метод потока перед завершением своей работы вызывает этот делегат обратного вызова.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [Работа с потоками](index.md)
- [Использование потоков и работа с потоками](using-threads-and-threading.md)
