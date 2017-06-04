---
title: "failedQI MDA | Microsoft Docs"
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
  - "failed QueryInterface"
  - "FailedQI MDA"
  - "QueryInterface call failures"
  - "MDAs (managed debugging assistants), failed QueryInterface"
  - "managed debugging assistants (MDAs), failed QueryInterface"
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# failedQI MDA
Помощник по отладке управляемого кода \(MDA\) `failedQI` активируется, когда среда выполнения вызывает `QueryInterface`в указателе интерфейса СОМ от имени вызываемой оболочки времени выполнения \(RCW\), и вызов `QueryInterface` завершается с ошибкой.  
  
## Признаки  
 Произошел сбой приведения в RCW, или вызов COM из RCW неожиданно завершается ошибкой.  
  
## Причина  
  
-   Вызов выполняется из неправильного контекста.  
  
-   Зарегистрированному прокси\-серверу не удается выполнить вызов `QueryInterface`, поскольку вызов выполнялся из неправильного контекста.  
  
-   Прокси\-сервер, принадлежащий OLE, возвратил значение HRESULT, указывающее на сбой.  
  
## Решение  
 Правила COM см. в документации MSDN.  
  
## Влияние на среду выполнения  
 Если вызов `QueryInterface` завершается с ошибкой, контекст переключается и предпринимается попытка повторно выполнить вызов `QueryInterface`, чтобы увидеть, не использовался ли при сбое неправильный контекст.  
  
## Вывод  
 Управляемое имя интерфейса, идентификатор GUID интерфейса и значение HRESULT ошибки.  
  
## Конфигурация  
  
```  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)