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
ms.openlocfilehash: 18b2a5a95756ed125d26b2846c0b1ddc320463ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181742"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="fb5e2-102">streamWriterBufferedDataLost MDA</span><span class="sxs-lookup"><span data-stu-id="fb5e2-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="fb5e2-103">Помощник по отладке управляемого кода (MDA) `streamWriterBufferedDataLost` активируется при записи в <xref:System.IO.StreamWriter>, если методы <xref:System.IO.StreamWriter.Flush%2A> или <xref:System.IO.StreamWriter.Close%2A> после этого не вызываются до уничтожения экземпляра <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="fb5e2-104">Если этот помощник по отладке управляемого кода включен, среда выполнения определяет, существуют ли до сих пор какие-либо буферизованные данные в <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="fb5e2-105">Если буферизованные данные существуют, помощник по отладке управляемого кода активируется.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="fb5e2-106">Вызов методов <xref:System.GC.Collect%2A> и <xref:System.GC.WaitForPendingFinalizers%2A> может принудительно вызвать методы завершения.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="fb5e2-107">В противном случае методы завершения будут выполняться в произвольные моменты времени и, возможно, вовсе не в момент завершения работы процесса.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="fb5e2-108">Выполнение методов завершения явным образом, когда данный помощник по отладке управляемого кода включен, способствует более надежному воспроизведению проблемы такого типа.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fb5e2-109">Симптомы</span><span class="sxs-lookup"><span data-stu-id="fb5e2-109">Symptoms</span></span>  
 <span data-ttu-id="fb5e2-110"><xref:System.IO.StreamWriter> не записывает последние 1–4 КБ данных в файл.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fb5e2-111">Причина</span><span class="sxs-lookup"><span data-stu-id="fb5e2-111">Cause</span></span>  
 <span data-ttu-id="fb5e2-112"><xref:System.IO.StreamWriter> осуществляет внутреннюю буферизацию данных. Для этого требуется, чтобы метод <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> вызывался для записи буферизованных данных в базовое хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="fb5e2-113">Если метод <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> не вызывается должным образом, данные, буферизованные в экземпляре <xref:System.IO.StreamWriter>, возможно, будут записаны некорректно.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="fb5e2-114">Ниже приведен пример неправильно написанного кода, который помощник по отладке управляемого кода должен перехватить.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="fb5e2-115">Предыдущий код активирует помощник по отладке управляемого кода более надежно, если сборка мусора запускается, а затем останавливается до того, как закончат работу методы завершения.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="fb5e2-116">Чтобы отследить проблему такого типа, можно добавить приведенный ниже код в конец предыдущего метода в отладочной сборке.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="fb5e2-117">Это поможет уверенно активировать этот помощник по отладке управляемого кода, но, конечно, не устранит причины возникновения проблемы.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="fb5e2-118">Решение</span><span class="sxs-lookup"><span data-stu-id="fb5e2-118">Resolution</span></span>  
 <span data-ttu-id="fb5e2-119">Следует обязательно вызывать <xref:System.IO.StreamWriter.Close%2A> или <xref:System.IO.StreamWriter.Flush%2A> для <xref:System.IO.StreamWriter>, прежде чем закрывать приложение или любой блок кода, в котором есть экземпляр <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="fb5e2-120">Один из лучших способов для этого — создать экземпляр с блоком C# `using` (`Using` в Visual Basic), что обеспечивает вызов метода <xref:System.IO.StreamWriter.Dispose%2A> для средства записи, в результате чего экземпляр закрывается корректно.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="fb5e2-121">В приведенном ниже примере кода демонстрируется то же самое решение, но достигаемое с помощью `try/finally` вместо `using`.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
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
  
 <span data-ttu-id="fb5e2-122">Если невозможно использовать ни одно из этих решений (например, если <xref:System.IO.StreamWriter> хранится в статической переменной и нельзя просто запустить код в конце его времени существования), в таком случае можно избежать возникновения данной проблемы, вызвав <xref:System.IO.StreamWriter.Flush%2A> для <xref:System.IO.StreamWriter> после его последнего использования и присвоив свойству <xref:System.IO.StreamWriter.AutoFlush%2A> значение `true` перед его первым использованием.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
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
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fb5e2-123">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="fb5e2-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="fb5e2-124">Этот MDA не оказывает никакого влияния на среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fb5e2-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fb5e2-125">Output</span></span>  
 <span data-ttu-id="fb5e2-126">Сообщение о том, что произошло данное нарушение.</span><span class="sxs-lookup"><span data-stu-id="fb5e2-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fb5e2-127">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="fb5e2-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb5e2-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fb5e2-128">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="fb5e2-129">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="fb5e2-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
