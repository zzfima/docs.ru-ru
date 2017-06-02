---
title: "invalidGCHandleCookie MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid cookies"
  - "cookies, invalid"
  - "managed debugging assistants (MDAs), invalid cookies"
  - "InvalidGCHandleCookie MDA"
  - "invalid cookies"
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# invalidGCHandleCookie MDA
Управляемый помощник по отладке \(MDA\) `invalidGCHandleCookie` активируется в случае попытки преобразования из недопустимого файла cookie <xref:System.IntPtr> в <xref:System.Runtime.InteropServices.GCHandle>.  
  
## Признаки  
 Неопределенное поведение, например, нарушение прав доступа или повреждение памяти, во время попытки использования или извлечения <xref:System.Runtime.InteropServices.GCHandle> из <xref:System.IntPtr>.  
  
## Причина  
 Файл cookie, вероятно, является недопустимым, поскольку он не был изначально создан из <xref:System.Runtime.InteropServices.GCHandle>; представляет <xref:System.Runtime.InteropServices.GCHandle>, который уже был освобожден; является файлом cookie для <xref:System.Runtime.InteropServices.GCHandle> в другом домене приложения; был маршалирован в исходный код в качестве <xref:System.Runtime.InteropServices.GCHandle>, но был передан обратно среде CLR в качестве <xref:System.IntPtr> при попытке преобразования.  
  
## Решение  
 Следует указать допустимый файл cookie <xref:System.IntPtr> для <xref:System.Runtime.InteropServices.GCHandle>.  
  
## Влияние на среду выполнения  
 При включении данного MDA отладчик больше не может прослеживать корни приложения до их объектов, поскольку значения cookie, переданные обратно, отличаются от значений, возвращаемых при отключенном MDA.  
  
## Output  
 Сообщение о недопустимых значениях cookie <xref:System.IntPtr>.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>   
 <xref:System.Runtime.InteropServices.GCHandle>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)