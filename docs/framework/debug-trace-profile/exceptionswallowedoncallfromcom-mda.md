---
title: "exceptionSwallowedOnCallFromCom MDA | Microsoft Docs"
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
  - "messages, informational"
  - "informational messages"
  - "managed debugging assistants (MDAs), exceptions"
  - "exception handling, managed debugging assistants"
  - "MDAs (managed debugging assistants), exceptions"
  - "ExceptionSwallowedOnCallFromCOM MDA"
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# exceptionSwallowedOnCallFromCom MDA
Помощник отладки управляемого кода \(MDA\) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.  
  
## Признаки  
 Вызов управляемого компонента из COM возвращает значение FALSE или 0.  Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать.  В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.  
  
## Причина  
 Возникло исключение, однако не существует приемлемого способа сообщить об этом.  
  
## Решение  
 Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.  
  
## Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  Он только выводит данные об исключениях, перехваченных без предупреждения.  
  
## Вывод  
 Информационное сообщение с именем метода, именем типа и указанием на исключение.  
  
## Конфигурация  
  
```  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)