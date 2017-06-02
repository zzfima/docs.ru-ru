---
title: "reportAvOnComRelease MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), reference counting errors"
  - "exceptions, reference counting errors"
  - "ReportAvOnComRelease MDA"
  - "COM release access violations"
  - "user reference counting errors"
  - "managed debugging assistants (MDAs), reference counting errors"
  - "report access violation on Com release"
  - "reference counting errors"
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# reportAvOnComRelease MDA
Помощник отладки управляемого кода \(MDA\) `reportAvOnComRelease` активируется при возникновении исключений, вызванных ошибками подсчета пользовательских ссылок при выполнении COM\-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.  
  
## Признаки  
 Нарушения прав доступа и повреждение памяти.  
  
## Причина  
 Иногда исключение возникает в связи с ошибками подсчета пользовательских ссылок при выполнении COM\-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.  Обычно это исключение отменяется, так как в противном случае в среде CLR произойдет нарушение прав доступа, и работа среды будет завершена.  Когда этот помощник включен, такие исключения вместо простой отмены можно обнаруживать и выводить в отчетах.  
  
## Решение  
 Изучите свой код подсчета ссылок для поиска ошибок и проверки собственных клиентов объекта на наличие ошибок подсчета ссылок.  
  
## Влияние на среду выполнения  
 Доступно два режима.  Если атрибут `allowAv` имеет значение `true`, помощник запрещает среде выполнения отменить нарушение прав доступа.  Если `allowAv` имеет значение `false`, которое используется по умолчанию, среды выполнения отменяет нарушение прав доступа, однако пользователь получает предупреждение о возникновении и отмене исключения.  
  
## Вывод  
 Когда это возможно, выходные данные содержат исходный vtable указателя интерфейса COM.  В противном случае отображается информационное сообщение.  
  
## Конфигурация  
  
```  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)