---
title: "invalidOverlappedToPinvoke MDA | Microsoft Docs"
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
  - "overlapped pointers"
  - "managed debugging assistants (MDAs), overlapped pointers"
  - "invalid overlapped pointer to platform invoke"
  - "InvalidOverlappedToPinvoke MDA"
  - "MDAs (managed debugging assistants), overlapped pointers"
  - "pointers, overlapped"
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidOverlappedToPinvoke MDA
Управляемый помощник по отладке \(MDA\) `invalidOverlappedToPinvoke` активируется, когда перекрывающийся указатель, созданный не в куче, где производится сборка мусора, передается определенным функциям Win32.  
  
> [!NOTE]
>  По умолчанию данный MDA активируется только в том случае, если в коде определен платформенный вызов, и отладчик выводит отчет о статусе JustMyCode для каждого метода.  Отладчик, который не понимает JustMyCode \(например, MDbg.exe без расширений\), не активирует данный MDA.  Данный MDA может быть включен для таких отладчиков с помощью файла конфигурации и настройки `justMyCode="false"` явным образом в файле MDA.CONFIG `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`\).  
  
## Признаки  
 Сбой или необъяснимые повреждения кучи.  
  
## Причина  
 Перекрывающийся указатель, не созданный в куче, в которой производится сборка мусора, передается определенным функциям операционной системы.  
  
 В следующей таблице приведены функции, которые отслеживает данный MDA:  
  
|Module|Функция|  
|------------|-------------|  
|HttpApi.dll|`HttpReceiveHttpRequest`|  
|IpHlpApi.dll|`NotifyAddrChange`|  
|kernel32.dll|`ReadFile`|  
|kernel32.dll|`ReadFileEx`|  
|kernel32.dll|`WriteFile`|  
|kernel32.dll|`WriteFileEx`|  
|kernel32.dll|`ReadDirectoryChangesW`|  
|kernel32.dll|`PostQueuedCompletionStatus`|  
|MSWSock.dll|`ConnectEx`|  
|WS2\_32.dll|`WSASend`|  
|WS2\_32.dll|`WSASendTo`|  
|WS2\_32.dll|`WSARecv`|  
|WS2\_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 Вероятность повреждения кучи в данных условиях высока, поскольку <xref:System.AppDomain>, совершающий вызов, может быть выгружен.  Если происходит выгрузка <xref:System.AppDomain>, код приложения либо освободит память, выделенную для перекрывающегося указателя, что приведет к повреждению при завершении операции, либо произойдет утечка памяти, что приведет к проблемам в дальнейшем.  
  
## Решение  
 Следует использовать объект <xref:System.Threading.Overlapped>, вызывающий метод <xref:System.Threading.Overlapped.Pack%2A>, чтобы получить структуру <xref:System.Threading.NativeOverlapped>, которую можно передать в функцию.  Если происходит выгрузка <xref:System.AppDomain>, среда CLR ожидает завершения асинхронной операции, прежде чем освободить указатель.  
  
## Влияние на среду выполнения  
 Данный MDA не оказывает влияния на среду CLR.  
  
## Output  
 Следующий пример демонстрирует результат действия данного MDA:  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)