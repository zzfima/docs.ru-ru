---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: 628d6a96606117d447c61d01595d13dd4a957ce4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138115"
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType> представляет собой примитив синхронизации, снимающий блокировку потоков в состоянии ожидания после определенного числа сигналов. <xref:System.Threading.CountdownEvent> предназначен для таких ситуаций, в которых он может заменить вызовы <xref:System.Threading.ManualResetEvent> или <xref:System.Threading.ManualResetEventSlim> с ручным уменьшением значения переменной перед подачей сигнала о событии. Например, в алгоритме ветвления и соединения вы можете создать <xref:System.Threading.CountdownEvent> со значением 5 для счетчика сигналов, а затем запустить пять рабочих элементов в пуле потоков, каждый из которых будет вызывать <xref:System.Threading.CountdownEvent.Signal%2A> после завершения работы. Каждый вызов <xref:System.Threading.CountdownEvent.Signal%2A> уменьшает значение счетчика на 1. В основном потоке вызов <xref:System.Threading.CountdownEvent.Wait%2A> блокируется до тех пор, пока значение счетчика не достигнет нуля.  
  
> [!NOTE]
> Если ваш код не будет взаимодействовать с устаревшими API синхронизации платформы .NET Framework, вы можете еще проще реализовать параллелизм ветвления-соединения с помощью объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или метода <xref:System.Threading.Tasks.Parallel.Invoke%2A>.  
  
 <xref:System.Threading.CountdownEvent> предоставляет следующие дополнительные возможности:  
  
- Операцию ожидания можно отменить с помощью маркеров отмены.  
  
- Значение счетчика можно увеличивать после создания экземпляра.  
  
- Экземпляры можно использовать повторно после того, как <xref:System.Threading.CountdownEvent.Wait%2A> завершает работу и вызывает метод <xref:System.Threading.CountdownEvent.Reset%2A>.  
  
- Экземпляры поддерживают <xref:System.Threading.WaitHandle> для интеграции с другими API синхронизации платформы .NET Framework, например <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Основное использование  
 В следующем примере демонстрируется применение рабочих элементов <xref:System.Threading.CountdownEvent> и <xref:System.Threading.ThreadPool>.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent с возможностью отмены  
 В примере ниже показано, как отменить операцию ожидания для <xref:System.Threading.CountdownEvent> с помощью маркера отмены. Базовый шаблон соответствует универсальной модели отмены, которая применяется на платформе .NET Framework 4. См. дополнительные сведения об [отмене в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Обратите внимание, что операция ожидания не отменяет потоки, отправляющие сигналы. Как правило, отмена применяется к логической операции, которая включает ожидание событий и все рабочие элементы, которые она синхронизирует. В этом примере каждому рабочему элементу передается копия маркера отмены, чтобы элемент выполнил необходимые действия для завершения работы.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
