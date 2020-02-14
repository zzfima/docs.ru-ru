---
title: callbackOnCollectedDelegate MDA
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
ms.openlocfilehash: eb14e0df5396d92eb223dde2e562684c4c318295
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217570"
---
# <a name="callbackoncollecteddelegate-mda"></a>callbackOnCollectedDelegate MDA
Управляемый помощник по отладке (MDA) `callbackOnCollectedDelegate` активируется, если делегат маршалируется из управляемого в неуправляемый код как указатель функции, и обратный вызов помещается в данный указатель функции после сбора мусора делегата.  
  
## <a name="symptoms"></a>Симптомы  
 Нарушение прав доступа происходит при попытке вызова управляемого кода посредством указателей функций, которые были получены из управляемых делегатов. Такие сбои, не будучи распространенными ошибками среды CLR, могут возникать из-за нарушения прав доступа в коде среды CLR.  
  
 Этот сбой не является постоянным; иногда вызов указателя функции выполняется успешно, а иногда происходит сбой. Этот сбой может возникать только в условиях большой нагрузки или при произвольном числе попыток.  
  
## <a name="cause"></a>Причина  
 Делегат, из которого указатель функции был создан и открыт для неуправляемого кода, был собран как мусор. Когда неуправляемый компонент пытается вызвать указатель функции, он создает нарушение прав доступа.  
  
 Этот сбой появляется произвольно, так как он зависит от того, когда выполняется сборка мусора. Если делегат является доступным для коллекции, сборка мусора может произойти после обратного вызова, и тогда вызов выполняется успешно. В других случаях сборка мусора происходит перед обратным вызовом, обратный вызов создает нарушение прав доступа, и программа останавливается.  
  
 Вероятность возникновения сбоя зависит от времени между маршалингом делегата и обратным вызовом указателя функции, а также от частоты выполнения сборки мусора. Этот сбой бывает разовым при коротком промежутке времени между маршалингом делегата и выполнением обратного вызова. Обычно так происходит, если неуправляемый метод, получающий указатель функции, не сохраняет этот указатель функции для дальнейшего использования, а вместо этого выполняет обратный вызов указателя функции немедленно для завершения работы перед возвратом. Аналогично сборка мусора происходит чаще, если система работает в условиях большой нагрузки, что увеличивает вероятность того, что сборка мусора произойдет перед выполнением обратного вызова.  
  
## <a name="resolution"></a>Решение  
 Когда делегат маршалируется как указатель функции, сборщик мусора не может отслеживать его время существования. Вместо этого код должен хранить ссылку на делегат в течение времени существования неуправляемого указателя функции. Однако прежде чем делать это, необходимо определить, какой делегат был собран. При активации MDA он предоставляет имя типа делегата. Используйте это имя для поиска в коде платформенного вызова или в сигнатурах COM, которые передают этот делегат в неуправляемый код. Делегат, вызвавший ошибку, передается вовне посредством одного из этих мест вызова. Можно также включить в MDA `gcUnmanagedToManaged` принудительный запуск сборки мусора перед каждым обратным вызовом в среде выполнения. Это удалит неопределенность, вносимую сбором мусора, так как обеспечит сбор мусора всегда перед обратным вызовом. Если известно, какой делегат был собран, измените код, чтобы сохранить ссылку на этот делегат на управляемой стороне в течение времени существования маршалированного неуправляемого указателя функции.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Если делегаты маршалируются как указатели функций, среда выполнения выделяет преобразователя, который осуществляет переход от неуправляемого указателя к управляемому. Этот преобразователь — то, что неуправляемый код фактически вызывает перед финальным вызовом управляемого делегата. Без включения MDA `callbackOnCollectedDelegate` неуправляемый код маршалинга удаляется после сбора делегата. С включением MDA `callbackOnCollectedDelegate` неуправляемый код маршалинга не удаляется немедленно после сбора делегата. Вместо этого последние 1000 экземпляров хранятся по умолчанию и изменяются, чтобы активировать MDA при вызове. Преобразователь в конечном счете удаляется после сбора не менее чем 1001 маршалированного делегата.  
  
## <a name="output"></a>Вывод  
 MDA сообщает имя типа собранного делегата до попытки обратного вызова в его неуправляемом указателе функции.  
  
## <a name="configuration"></a>Конфигурация  
 В следующем примере показаны параметры конфигурации приложения. В нем устанавливается число преобразователей, которые сохраняются MDA, равное 1500. Значение `listSize` по умолчанию — 1000; минимальное значение — 50; максимальное значение — 2000.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует ситуацию, которая может активировать данный MDA:  
  
```cpp
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}
```

```csharp
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
- [gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)
