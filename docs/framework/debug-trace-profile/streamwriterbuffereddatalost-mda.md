---
title: "streamWriterBufferedDataLost MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "StreamWriter class, data buffering problems"
  - "managed debugging assistants (MDAs), StreamWriter data buffering"
  - "buffers, StreamWriter problems"
  - "MDAs (managed debugging assistants), StreamWriter data buffering"
  - "StreamWriter buffered data lost"
  - "data buffering problems"
  - "streamWriterBufferedDataLost MDA"
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# streamWriterBufferedDataLost MDA
Управляемый помощник по отладке \(MDA\) `streamWriterBufferedDataLost` активируется при записи в <xref:System.IO.StreamWriter>, но методы <xref:System.IO.StreamWriter.Flush%2A> или <xref:System.IO.StreamWriter.Close%2A> после этого не вызываются до уничтожения экземпляра <xref:System.IO.StreamWriter>.  Если данный MDA включен, среда выполнения определяет, существуют ли до сих пор какие\-либо буферизованные данные в <xref:System.IO.StreamWriter>.  Если буферизованные данные существуют, MDA активируется.   Вызов методов <xref:System.GC.Collect%2A> и <xref:System.GC.WaitForPendingFinalizers%2A> может принудительно вызвать метод завершения.   В других случаях методы завершения будут выполняться в произвольные моменты времени, и, возможно, вовсе не в момент завершения работы процесса.  Выполнение методов завершения явным образом, когда данный MDA включен, способствует более надежному воспроизведению проблемы такого типа.  
  
## Признаки  
 <xref:System.IO.StreamWriter> не записывает последние 1\-4 КБ данных в файл.  
  
## Причина  
 <xref:System.IO.StreamWriter> буферизует данные внутренне; для этого требуется, чтобы методы <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> вызывались для записи буферизованных данных в основное хранилище данных.  Если <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> не вызываются должным образом, данные, буферизованные в экземпляре <xref:System.IO.StreamWriter>, возможно, будут записаны некорректно.  
  
 Далее приведен пример некорректно написанного кода, который MDA должен перехватить:  
  
```  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 Предыдущий код активирует данный MDA более надежно, если коллекция мусора запущена и затем остановлена до того, как завершат работу методы завершения.  Чтобы отследить проблему такого типа, можно добавить следующий код в конец предыдущего метода в отладочном построении.   Это поможет уверенно активировать этот MDA, но, конечно, не устранит причины возникновения проблемы.  
  
```  
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## Решение  
 Следует обязательно вызывать <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> на <xref:System.IO.StreamWriter> прежде, чем закрыть приложение или любой блок кода, в котором есть экземпляр <xref:System.IO.StreamWriter>.  Добиться этого проще всего с помощью создания экземпляра с блоком C\# `using` \(`Using` в Visual Basic\), что обеспечивает вызов метода <xref:System.IO.StreamWriter.Dispose%2A> для средства записи, в результате чего экземпляр закрывается корректно.  
  
```  
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 Следующий пример кода демонстрирует то же самое решение, но при помощи `try/finally` вместо `using`:  
  
```  
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
  
 Если невозможно использовать ни одно из этих решений \(например, если <xref:System.IO.StreamWriter> хранится в статической переменной, и нельзя просто запустить код в конце его времени существования\), в таком случае можно избежать возникновения данной проблемы, вызвав <xref:System.IO.StreamWriter.Flush%2A> для <xref:System.IO.StreamWriter> после его последнего использования и присвоив свойству <xref:System.IO.StreamWriter.AutoFlush%2A> значение `true` перед его первым использованием.  
  
```  
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
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не влияет на среду выполнения.  
  
## Output  
 Сообщение о том, что произошло данное нарушение.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.IO.StreamWriter>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)