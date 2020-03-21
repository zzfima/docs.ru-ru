---
title: MDA с возможностью повторного входа
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
ms.openlocfilehash: 5cbe8e843ad72785010240f3db30b1d344c80650
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181768"
---
# <a name="reentrancy-mda"></a>MDA с возможностью повторного входа
Помощник по отладке управляемого кода `reentrancy` (MDA) активируется при попытке выполнить переход из машинного кода в управляемый в тех случаях, когда ранее не был выполнен упорядоченный переход из управляемого кода в машинный.  
  
## <a name="symptoms"></a>Симптомы  
 При переходе из машинного кода в управляемый повреждается куча объекта или возникает другая серьезная ошибка.  
  
 Переход в потоке между управляемым и машинным кодом в любом направлении должен быть упорядоченным. Тем не менее для некоторых низкоуровневых точек расширения в операционной системе, таких как векторный обработчик исключений, допускается неупорядоченный переход из управляемого кода в машинный.  Такие переходы осуществляются под управлением операционной системы, а не общеязыковой среды управления (CLR).  В любом машинном коде, который выполняется внутри таких точек расширения, не рекомендуется выполнять обратные вызовы управляемого кода.  
  
## <a name="cause"></a>Причина  
 Низкоуровневая точка расширения операционной системы, например векторный обработчик исключений, активирована при выполнении управляемого кода.  Код приложения, который вызывается посредством этой точки расширения, пытается выполнить обратный вызов управляемого кода.  
  
 Эта проблема всегда связана с кодом приложения.  
  
## <a name="resolution"></a>Решение  
 Проверьте трассировку стека для потока, который вызвал помощник по отладке управляемого кода.  Поток пытается выполнить недопустимый вызов управляемого кода.  В трассировке стека должны быть представлены код приложения, использующий эту точку расширения, предоставляющий ее код операционной системы, а также управляемый код, который был прерван этой точкой расширения.  
  
 Например, этот помощник по отладке управляемого кода активируется при попытке вызвать управляемый код из векторного обработчика исключений.  В стеке будут показаны код обработки исключения операционной системы, а также управляемый код, который вызывает исключение, например <xref:System.DivideByZeroException> или <xref:System.AccessViolationException>.  
  
 В этом примере следует полностью реализовать векторный обработчик исключений в неуправляемом коде.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  
 Помощник по отладке управляемого кода сообщает о попытке недопустимого повторного входа.  Проверьте стек потока, чтобы понять, почему это происходит и как решить проблему. Далее приводится образец вывода.  
  
```output
Additional Information: Attempting to call into managed code without
transitioning out first.  Do not attempt to run managed code inside
low-level native extensibility points. Managed Debugging Assistant
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере кода возникает исключение <xref:System.AccessViolationException>.  В версиях Windows, которые поддерживают векторную обработку исключений, будет вызван управляемый векторный обработчик исключений.  Если помощник по отладке управляемого кода `reentrancy` включен, он будет активирован при попытке выполнить вызов `MyHandler` из кода векторной обработки исключений операционной системы.  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try
        {  
            // Dispatch on null should AV.  
            Reenter r = null;
            r.Run();  
        }
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
