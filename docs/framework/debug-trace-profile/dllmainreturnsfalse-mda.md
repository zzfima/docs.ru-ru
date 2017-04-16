---
title: "dllMainReturnsFalse MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), DllMain returns false"
  - "DllMainReturnsFalse MDA"
  - "DllMain function"
  - "MDAs (managed debugging assistants), DllMain returns false"
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# dllMainReturnsFalse MDA
Помощник по отладке управляемого кода \(MDA\) `dllMainReturnsFalse` активируется в случае, если управляемая функция `DllMain` пользовательской сборки, вызванная с помощью DLL\_PROCESS\_ATTACH, возвращает значение FALSE.  
  
## Признаки  
 Функция `DllMain` возвратила значение FALSE, указывающее на то, что функция не была выполнена корректно.  Это может вызвать неопределенные проблемы, поскольку функции `DllMain`, как правило, содержат важный код инициализации.  
  
## Причина  
 Функция `DllMain` вызывается с помощью DLL\_PROCESS\_ATTACH для инициализации DLL при загрузке.  Если функция возвращает значение FALSE, это означает, что не удалось инициализировать библиотеку DLL.  
  
## Решение  
 Следует проанализировать код функции `DllMain` проблемной библиотеки DLL и выявить причину сбоя инициализации.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  Он только выводит сведения о возвращаемых значениях для функции `DllMain`.  
  
## Output  
 Сообщение о том, что функция `DllMain`, вызываемая с помощью DLL\_PROCESS\_ATTACH, вернула значение FALSE.  Обратите внимание, что данный помощник по отладке управляемого кода активируется только в случае, если `DllMain` реализуется в управляемом коде.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)