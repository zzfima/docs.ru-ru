---
title: streamWriterBufferedDataLost MDA
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 82940b40b302f4a928547f2e6a0c285727e13934
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216105"
---
# <a name="streamwriterbuffereddatalost-mda"></a>streamWriterBufferedDataLost MDA
Помощник по отладке управляемого кода (MDA) `streamWriterBufferedDataLost` активируется при записи в <xref:System.IO.StreamWriter>, если методы <xref:System.IO.StreamWriter.Flush%2A> или <xref:System.IO.StreamWriter.Close%2A> после этого не вызываются до уничтожения экземпляра <xref:System.IO.StreamWriter>. Если этот помощник по отладке управляемого кода включен, среда выполнения определяет, существуют ли до сих пор какие-либо буферизованные данные в <xref:System.IO.StreamWriter>. Если буферизованные данные существуют, помощник по отладке управляемого кода активируется. Вызов методов <xref:System.GC.Collect%2A> и <xref:System.GC.WaitForPendingFinalizers%2A> может принудительно вызвать методы завершения. В противном случае методы завершения будут выполняться в произвольные моменты времени и, возможно, вовсе не в момент завершения работы процесса. Выполнение методов завершения явным образом, когда данный помощник по отладке управляемого кода включен, способствует более надежному воспроизведению проблемы такого типа.  
  
## <a name="symptoms"></a>Симптомы  
 <xref:System.IO.StreamWriter> не записывает последние 1–4 КБ данных в файл.  
  
## <a name="cause"></a>Причина  
 <xref:System.IO.StreamWriter> осуществляет внутреннюю буферизацию данных. Для этого требуется, чтобы метод <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> вызывался для записи буферизованных данных в базовое хранилище данных. Если метод <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> не вызывается должным образом, данные, буферизованные в экземпляре <xref:System.IO.StreamWriter>, возможно, будут записаны некорректно.  
  
 Ниже приведен пример неправильно написанного кода, который помощник по отладке управляемого кода должен перехватить.  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 Предыдущий код активирует помощник по отладке управляемого кода более надежно, если сборка мусора запускается, а затем останавливается до того, как закончат работу методы завершения. Чтобы отследить проблему такого типа, можно добавить приведенный ниже код в конец предыдущего метода в отладочной сборке. Это поможет уверенно активировать этот помощник по отладке управляемого кода, но, конечно, не устранит причины возникновения проблемы.  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a>Решение  
 Следует обязательно вызывать <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> для <xref:System.IO.StreamWriter>, прежде чем закрывать приложение или любой блок кода, в котором есть экземпляр <xref:System.IO.StreamWriter>. Один из лучших способов для этого — создать экземпляр с блоком C# `using` (`Using` в Visual Basic), что обеспечивает вызов метода <xref:System.IO.StreamWriter.Dispose%2A> для средства записи, в результате чего экземпляр закрывается корректно.  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 В приведенном ниже примере кода демонстрируется то же самое решение, но достигаемое с помощью `try/finally` вместо `using`.  
  
```csharp
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 Если невозможно использовать ни одно из этих решений (например, если <xref:System.IO.StreamWriter> хранится в статической переменной и нельзя просто запустить код в конце его времени существования), в таком случае можно избежать возникновения данной проблемы, вызвав <xref:System.IO.StreamWriter.Flush%2A> для <xref:System.IO.StreamWriter> после его последнего использования и присвоив свойству <xref:System.IO.StreamWriter.AutoFlush%2A> значение `true` перед его первым использованием.  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот MDA не оказывает никакого влияния на среду выполнения.  
  
## <a name="output"></a>Вывод  
 Сообщение о том, что произошло данное нарушение.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.IO.StreamWriter>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
