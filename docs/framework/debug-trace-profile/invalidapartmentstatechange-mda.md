---
title: "invalidApartmentStateChange MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid apartment state"
  - "managed debugging assistants (MDAs), invalid apartment state"
  - "InvalidApartmentStateChange MDA"
  - "invalid apartment state changes"
  - "threading [.NET Framework], apartment states"
  - "apartment states"
  - "threading [.NET Framework], managed debugging assistants"
  - "COM apartment states"
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# invalidApartmentStateChange MDA
Помощник по отладке управляемого кода \(MDA\) `invalidApartmentStateChange` активируется в случае возникновения одной из следующих проблем.  
  
-   Попытка изменить состояние контейнера СОМ в потоке, который уже был инициализирован моделью СОМ для другого состояния контейнера.  
  
-   Непредвиденное изменение состояния контейнера СОМ в потоке.  
  
## Признаки  
  
-   Состояние контейнера СОМ в потоке отличается от требуемого.  Вследствие этого прокси могут использоваться компонентами СОМ, потоковая модель которых отличается от текущей.  В свою очередь, это может стать причиной возникновения исключения <xref:System.InvalidCastException> при вызове объекта СОМ посредством интерфейсов, не настроенных для маршалинга между контейнерами.  
  
-   Состояние контейнера СОМ в потоке отличается от ожидаемого.  Это может стать причиной возникновения исключения <xref:System.Runtime.InteropServices.COMException> со значением RPC\_E\_WRONG\_THREAD для HRESULT, а также исключения <xref:System.InvalidCastException> при вызове [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\).  Это также может привести к тому, что несколько потоков будут иметь одновременный доступ к некоторым однопотоковым компонентам СОМ, что может стать причиной повреждения или потери данных.  
  
## Причина  
  
-   Поток был изначально инициализирован для другого состояния контейнера СОМ.  Следует отметить, что установить состояние контейнера для потока можно явным или неявным образом.  Чтобы определить состояние контейнера для потока явным образом, можно использовать свойство <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> и методы <xref:System.Threading.Thread.SetApartmentState%2A> и <xref:System.Threading.Thread.TrySetApartmentState%2A>.  Для потока, созданного неявным образом с помощью метода <xref:System.Threading.Thread.Start%2A>, устанавливается значение <xref:System.Threading.ApartmentState>, если только метод <xref:System.Threading.Thread.SetApartmentState%2A> не вызван до запуска потока.  Главный поток приложения также инициализируется неявным образом со значением <xref:System.Threading.ApartmentState>, если только для основного метода не определен атрибут <xref:System.STAThreadAttribute>.  
  
-   В потоке вызывается метод `CoUninitialize` \(или метод `CoInitializeEx`\) с другой моделью параллелизма.  
  
## Решение  
 Следует настроить состояние контейнера потока до его запуска или применить к основному методу приложения атрибут <xref:System.STAThreadAttribute> или <xref:System.MTAThreadAttribute>.  
  
 Во втором случае следует изменить код, вызывающий метод `CoUninitialize`, чтобы вызов был отложен до завершения работы потока и прекращения использования в потоке оболочек RCW и базовых компонентов СОМ.  Тем не менее, если невозможно изменить код, который вызывает метод `CoUninitialize`, то в этом случае не допускается использование оболочек RCW из потоков, которые не инициализированы таким образом.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  
  
## Output  
 Состояние контейнера СОМ текущего потока, а также состояние, которое пытался применить код.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода демонстрируется ситуация, в которой может активироваться данный помощник по отладке управляемого кода.  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)