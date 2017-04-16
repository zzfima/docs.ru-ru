---
title: "reentrancy MDA | Microsoft Docs"
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
  - "unmanaged code, debugging"
  - "transitioning threads unmanaged to managed code"
  - "reentrancy MDA"
  - "reentrancy without an orderly transition"
  - "managed debugging assistants (MDAs), reentrancy"
  - "illegal reentrancy"
  - "MDAs (managed debugging assistants), reentrancy"
  - "threading [.NET Framework], managed debugging assistants"
  - "managed code, debugging"
  - "native debugging, MDAs"
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# reentrancy MDA
Управляемый помощник по отладке \(MDA\) `reentrancy` активируется при попытке передачи из исходного в машинный код в случаях, когда не произошло предварительного переключения из управляемого в исходный код посредством надлежащей передачи.  
  
## Признаки  
 Куча объектов повреждена или возникли другие серьезные ошибки во время передачи из исходного в машинный код.  
  
 Потоки, которые переключаются между исходным и управляемым кодом в любом направлении, должны выполнять надлежащую передачу.   Однако определенные низкоуровневые точки расширения в операционной системе, такие как векторный обработчик исключений, позволяют переключения из исходного в машинный код без выполнения надлежащей передачи.  Эти переключения находятся под контролем системы, а не под контролем среды CLR.   Любой исходный код, который выполняется в данных точках расширения, должен избегать выполнения обратных вызовов в управляемый код.  
  
## Причина  
 Низкоуровневая точка расширения в операционной системе, такая как векторный обработчик исключений, активирована во время выполнения управляемого кода.  Код приложения, который вызывается посредством данной точки расширения, пытается выполнить обратный вызов в управляемый код.  
  
 Код приложения всегда является причиной возникновения данной проблемы.  
  
## Решение  
 Следует изучить трассировку стека для потока, который активировал этот MDA.   Поток пытается выполнить недопустимый вызов в управляемый код.   Трассировка стека должна отобразить код приложения с помощью точки расширения, кода операционной системы, который предоставляет данную точку расширения, и управляемого кода, который был прерван данной точкой расширения.  
  
 Например, MDA активируется при попытке вызвать управляемый код из векторного обработчика исключений.   В стеке отобразится код обработчика исключений операционной системы и некий управляемый код, вызывающий исключение, такое как <xref:System.DivideByZeroException> или <xref:System.AccessViolationException>.  
  
 Для данного примера верным решением будет реализация векторного обработчика исключений полностью в неуправляемом коде.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  
  
## Output  
 MDA сообщает о попытке недопустимого повторного входа.   Следует изучить стек потока, чтобы определить причину и способы решения проблемы.  Далее приводится пример вывода:  
  
```  
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода вызывается <xref:System.AccessViolationException>.  В версиях Windows, которые поддерживают векторную обработку исключений, это вызовет управляемый векторный обработчик исключений.   Если включен MDA `reentrancy`, он активируется во время попытки вызова `MyHandler` из кода поддержки векторного обработчика исключений операционной системы.  
  
```  
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
  
## См. также  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)